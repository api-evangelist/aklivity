# Aklivity (aklivity)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Aklivity provides the Zilla multi-protocol edge and service proxy for event-driven architectures, enabling seamless integration between web apps, IoT clients, and microservices with Apache Kafka via declaratively defined, stateless APIs. Zilla supports HTTP, gRPC, MQTT, SSE, and WebSocket protocols, translating them to and from Kafka without custom code or connectors. The Zilla Platform adds enterprise governance, observability, and self-service access management for Kafka deployments.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/aklivity/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - API Gateway, Apache Kafka, Event-Driven, IoT, Kafka Proxy, Multi-Protocol, Real-Time

## Timestamps

- **Created:** 2026-01-02
- **Modified:** 2026-04-19

## APIs

### Zilla Gateway
Zilla is a stateless, cloud-native multi-protocol edge and service proxy that enables seamless access to Apache Kafka through HTTP REST, gRPC, SSE, MQTT, and WebSocket protocols.

**Human URL:** [https://www.aklivity.io/](https://www.aklivity.io/)

#### Tags:

 - API Gateway, Apache Kafka, Event-Driven, Kafka Proxy, Multi-Protocol

#### Properties

- [Documentation](https://docs.aklivity.io/zilla/latest/)
- [GettingStarted](https://docs.aklivity.io/zilla/latest/getting-started/quickstart/)
- [GitHubRepository](https://github.com/aklivity/zilla)

### Zilla Platform
The Zilla Platform adds an enterprise management layer with API data products, Kafka governance policies, self-service developer portal, field-level encryption, and unified observability.

**Human URL:** [https://www.aklivity.io/platform](https://www.aklivity.io/platform)

#### Tags:

 - API Management, Developer Portal, Governance, Kafka Management, Observability

#### Properties

- [Documentation](https://docs.aklivity.io/)

### ZillaBase
ZillaBase is an event-driven backend framework for web, mobile, and AI applications built on Apache Kafka and Zilla.

**Human URL:** [https://github.com/aklivity/zillabase](https://github.com/aklivity/zillabase)

#### Tags:

 - Backend Framework, Event-Driven, Real-Time

#### Properties

- [Documentation](https://docs.aklivity.io/)
- [GitHubRepository](https://github.com/aklivity/zillabase)

## Common Properties

- [Website](https://www.aklivity.io/)
- [Documentation](https://docs.aklivity.io/zilla/latest/)
- [GettingStarted](https://docs.aklivity.io/zilla/next/getting-started/quickstart/)
- [GitHubOrganization](https://github.com/aklivity)
- [GitHubRepository](https://github.com/aklivity/zilla)
- [Pricing](https://www.aklivity.io/pricing)

## Features

| Name | Description |
|------|-------------|
| Multi-Protocol Kafka Access | Translates HTTP REST, gRPC, MQTT, SSE, and WebSocket protocols directly to Kafka topics without custom code, connectors, or middleware. |
| Declarative Configuration | Define gateways and protocol mappings via YAML configuration or AsyncAPI specifications, then deploy with Docker, Helm, or native binaries. |
| JWT Authentication and TLS | Built-in JWT token validation, TLS termination, and Kafka SASL support for securing API access to Kafka clusters. |
| Schema Validation | SIMD-optimized runtime schema validation for JSON, Avro, and Protobuf via Confluent Schema Registry or AWS Glue Schema Registry. |
| Observability | Metrics and logs exported to Prometheus and OpenTelemetry for unified visibility across Kafka API traffic. |
| Kafka Governance | Topic naming policies, runtime enforcement, schema compliance rules, and API data product versioning with rate limits via Zilla Platform. |
| Self-Service Developer Portal | API key and certificate management self-service portal for Kafka consumers and producers via Zilla Platform. |
| Field-Level Encryption | PII classification and field-level encryption for sensitive data in Kafka messages via Zilla Platform. |

## Use Cases

| Name | Description |
|------|-------------|
| HTTP to Kafka REST API | Expose Kafka topics as REST API endpoints, allowing any HTTP client to produce and consume Kafka messages without Kafka client libraries. |
| IoT MQTT to Kafka | Connect IoT devices using MQTT protocol directly to Kafka topics, eliminating the need for a separate MQTT broker. |
| gRPC to Kafka | Route gRPC calls from microservices to Kafka topics for event-driven inter-service communication. |
| Kafka Self-Service Platform | Platform teams build internal developer portals for Kafka access with governance, rate limiting, and self-service API key management. |
| Event-Driven Partner Integration | Enterprises expose Kafka event streams to external partners via secured, rate-limited REST or SSE APIs. |
| Financial Services Data Distribution | Financial institutions distribute real-time market data and trade events via secured Kafka API gateways. |

## Integrations

| Name | Description |
|------|-------------|
| Apache Kafka | Core integration — Zilla acts as a multi-protocol proxy in front of any Kafka cluster |
| AWS MSK | Managed Streaming for Apache Kafka integration with AWS-native security |
| Confluent Schema Registry | Schema validation and enforcement using Confluent Schema Registry |
| AWS Glue Schema Registry | Schema validation using AWS Glue Schema Registry |
| Prometheus | Metrics export for monitoring Zilla gateway performance |
| OpenTelemetry | Distributed tracing and observability via OpenTelemetry |
| AWS Secrets Manager | Secure credential management for Kafka and TLS configurations |

## JSON-LD

- [Aklivity Context](json-ld/aklivity-context.jsonld)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Zilla Gateway](capabilities/shared/zilla-gateway.yaml) — 2 operations for Kafka message production and consumption

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Kafka API Gateway](capabilities/kafka-api-gateway.yaml) | Zilla Gateway | 2 | Platform Engineer, API Developer, IoT Developer |

## Vocabulary

- [Aklivity Vocabulary](vocabulary/aklivity-vocabulary.yaml) — Unified taxonomy mapping 4 resources, 6 actions, 1 workflow, and 3 personas across operational and capability dimensions

## Rules

- [Aklivity Spectral Rules](rules/aklivity-spectral-rules.yml) — 11 rules across 6 categories enforcing Aklivity API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
