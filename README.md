# Aklivity

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

Aklivity builds Zilla, a stateless, source-available multi-protocol gateway for event-driven applications and AI agents. Zilla translates HTTP, SSE, WebSocket, MQTT, gRPC and MCP Streamable HTTP to and from Apache Kafka and other backends, configured declaratively in a zilla.yaml or driven directly from an OpenAPI or AsyncAPI document, with no custom code, connectors or separate MQTT broker. The Zilla MCP Gateway compiles OpenAPI specs, Kafka topics, Kafka Connect and schema registries into governed MCP tool sets that agents call through one authenticated endpoint. The Zilla Console adds an API and data-product catalog, a self-service developer portal, governance, audit and RBAC. Aklivity is a software vendor rather than a service operator: every Zilla runs inside the customer's own infrastructure, so there is no hosted Aklivity API and no Aklivity-issued credential.

**Areas:** AI Gateway · API Gateway · Agent Infrastructure · Apache Kafka · AsyncAPI · Event-Driven · IoT · Kafka Proxy · MCP · Multi-Protocol · Open Source · Real-Time

## Aklivity on APIs.io

Everything profiled for Aklivity is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/aklivity/](https://apis.io/providers/aklivity/)** — or go straight to one of the APIs or properties below.

### APIs (4)

- [Zilla Gateway](https://apis.io/apis/aklivity/zilla-gateway/) — Zilla is a stateless, cloud-native multi-protocol edge and service proxy that enables seamless access to Apache Kafka through HTTP REST, gRPC, SSE, MQTT,…
- [Zilla Platform](https://apis.io/apis/aklivity/zilla-platform/) — The Zilla Platform adds an enterprise management layer on top of Zilla Gateway, providing API data products with versioning and rate limits, Kafka…
- [Zilla MCP Gateway](https://apis.io/apis/aklivity/zilla-mcp-gateway/) — The Zilla MCP Gateway is the AI-facing face of the Zilla engine. It terminates Model Context Protocol Streamable HTTP from an agent and routes each tool…
- [ZillaBase](https://apis.io/apis/aklivity/zillabase/) — ZillaBase is an event-driven backend framework for the next generation of web, mobile, and AI applications, built on top of Apache Kafka and Zilla to enable…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### JSON Schema (1)

The data models the API reads and writes.

- [Namespace](https://apis.io/schemas/aklivity/aklivity-zilla-engine.schema/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Aklivity Context](https://apis.io/jsonld/aklivity/aklivity-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Aklivity Vocabulary](https://apis.io/vocabularies/aklivity/aklivity-vocabulary/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Aklivity API Rules](https://apis.io/rules/aklivity/aklivity-spectral-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Aklivity Authentication](https://apis.io/security/aklivity/aklivity-authentication/)
- [Aklivity Domain Security](https://apis.io/security/aklivity/aklivity-domain-security/)
- [Aklivity Vulnerability Disclosure](https://apis.io/security/aklivity/aklivity-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Aklivity Plans Pricing](https://apis.io/plans/aklivity/aklivity-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Aklivity Rate Limits](https://apis.io/rate-limits/aklivity/aklivity-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Aklivity Finops](https://apis.io/finops/aklivity/aklivity-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.aklivity.io/)
- [Documentation](https://docs.aklivity.io/latest/)
- [Getting started](https://docs.aklivity.io/latest/getting-started/)
- [API reference](https://docs.aklivity.io/latest/reference/2.x/)
- [Pricing](https://www.aklivity.io/pricing)
- [Support](https://docs.aklivity.io/latest/support/)
- [Blog](https://www.aklivity.io/blog)
- [Security](https://www.aklivity.io/security)
- [Terms of service](https://www.aklivity.io/terms-of-service)
- [Privacy policy](https://www.aklivity.io/privacy-policy)
- [GitHub](https://github.com/aklivity)

## API Evangelist rating

**Kin Score 48.6** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 62.5 |
| Contract quality | 13.9 |
| Contract governance | 41.7 |
| Operational transparency | 36.8 |
| Developer ergonomics | 70.7 |
| Access clarity | 63.2 |

**Agent readiness 14.4** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | unknown |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 30.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/aklivity/](https://apis.io/providers/aklivity/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Aklivity: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/aklivity/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
