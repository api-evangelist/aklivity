# Aklivity (aklivity)
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
