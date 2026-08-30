---
name: Expose a Kafka topic as a REST API with Zilla
description: >-
  Stand up a Zilla gateway that lets any HTTP client read from and write to an
  Apache Kafka topic, with idempotent writes and correlated request-response,
  without Kafka client libraries or Kafka Connect.
api: Zilla Gateway
provider: Aklivity
generated: '2026-08-30'
method: generated
grounding: >-
  Every binding name, option path and default in this skill is read from the
  Zilla 2.x configuration reference and from engine.schema.json, harvested to
  json-schema/aklivity-zilla-engine.schema.json. There are no operationIds here
  because Aklivity publishes no OpenAPI — the unit of work in this product is a
  named binding in zilla.yaml, not a REST operation.
operations:
  - binding: http (kind server)
  - binding: http-kafka (kind proxy)
  - binding: kafka (kind cache_client / cache_server)
  - binding: tcp (kind client)
  - cli: zilla start
  - cli: zilla logs
---

# Expose a Kafka topic as a REST API with Zilla

## When to use this

You have a Kafka topic and a consumer that speaks HTTP, not Kafka — a browser,
a partner, a mobile client, or an agent. Zilla terminates HTTP and mediates to
Kafka directly, so you do not deploy Kafka Connect, write a bridge service, or
hand out Kafka credentials.

Reference: https://docs.aklivity.io/latest/kafka-gateway/

## The pipeline

A `zilla.yaml` is a chain of named bindings. Each binding does one thing and
names its `exit` — the next binding. For HTTP-to-Kafka the chain is:

    tcp server -> http server -> http-kafka proxy -> kafka cache_client -> kafka client -> tcp client

Reference: https://docs.aklivity.io/latest/reference/2.x/config/bindings/

## Steps

1. **Write the routes on the `http-kafka` proxy binding.** Each route matches on
   `when[].method` and `when[].path` and declares a `with.capability` of either
   `fetch` (read a topic) or `produce` (write to a topic).

   ```yaml
   http_kafka_proxy:
     type: http-kafka
     kind: proxy
     routes:
       - when:
           - method: GET
             path: /items
         exit: kafka_cache_client
         with:
           capability: fetch
           topic: items-snapshots
           merge:
             content-type: application/json
       - when:
           - method: GET
             path: /items/{id}
         exit: kafka_cache_client
         with:
           capability: fetch
           topic: items-snapshots
           filters:
             - key: ${params.id}
   ```

   Reference: https://docs.aklivity.io/latest/reference/2.x/config/bindings/http-kafka/proxy.html

2. **Turn on idempotency before you expose any write route.** The `http-kafka`
   binding reads an idempotency key from a request header, so a client retry
   does not produce a duplicate record.

   ```yaml
   options:
     idempotency:
       header: idempotency-key   # this is the default; override it if your clients use another name
   ```

   Note what is NOT published: the retention window for a seen key. Treat replay
   protection as bounded by your own topic retention, and do not promise callers
   a window Aklivity has not stated. See
   `conventions/aklivity-conventions.yml`.

3. **For request-response, configure correlation.** A `produce` route can carry
   `reply-to`, `async` and `correlation-id`, and Zilla injects Kafka headers for
   them.

   ```yaml
   options:
     correlation:
       headers:
         reply-to: zilla:reply-to               # default
         correlation-id: zilla:correlation-id   # default
   routes:
     - when:
         - method: PUT
           path: /items/{id}
         - method: GET
           path: /items/{id};cid={correlationId}
       exit: kafka_cache_client
       with:
         capability: produce
         topic: items-requests
         acks: leader_only
         key: ${params.id}
         reply-to: items-responses
         async:
           location: /items/${params.id};cid=${correlationId}
   ```

4. **Guard the route.** Declare a guard once under `guards:` and reference it
   from `routes[].guarded`. `jwt` is available in the free Community edition;
   `oauth`, `api-keys`, `azure-ad`, `aws-cognito`, `aws-iam`, `aws-lambda` and
   `x509` are Plus. See `authentication/aklivity-authentication.yml`.

5. **Validate the payload.** Attach a model (`json`, `avro`, `protobuf`) via a
   catalog — Confluent, Karapace, Apicurio, AWS Glue, filesystem or inline.
   Failures surface as `MODEL_JSON_VALIDATION_FAILED`,
   `MODEL_AVRO_VALIDATION_FAILED` or `MODEL_PROTOBUF_VALIDATION_FAILED`.

6. **Check the config before you ship it.** `engine.schema.json` is JSON Schema
   draft 2019-09 — validate `zilla.yaml` against it in CI. The Zilla VS Code
   extension (`aklivity.zilla-vscode-ext`) renders the same graph as a diagram
   and flags missing connections. This is the only rehearsal path this product
   has; there is no data-plane dry run.

7. **Run it.**

   ```sh
   docker run -v ./zilla.yaml:/etc/zilla/zilla.yaml ghcr.io/aklivity/zilla:latest start -ve
   ```

   Reference: https://docs.aklivity.io/latest/deployment/install-zilla/docker.html

8. **Confirm it started.** `zilla logs` without `-f` prints the current log and
   exits, which the docs call out as usable as a Docker `HEALTHCHECK`. Look for
   `engine.started`.

## Rolling it back

Zilla is stateless and declaratively configured. To undo a change, restore the
previous `zilla.yaml` — auto-reconfigure watches the config source and re-applies
on change. To remove the deployment entirely: `docker stop` / `docker rm`, or
`helm uninstall [RELEASE_NAME]`. No time window applies to any of these.

What you CANNOT roll back this way is a record already produced to Kafka. That
is your topic and your application's problem, not the gateway's.

## Version trap

If you install via `brew install zilla` you will get the formula's pinned
0.9.159, which predates the 2.0.0 config format. A `zilla.yaml` written against
the 2.x reference will not run on it. Use the container image, or read
https://docs.aklivity.io/latest/deployment/migrating-to-2.x/ first.
