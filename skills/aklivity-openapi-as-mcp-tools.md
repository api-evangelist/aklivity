---
name: Turn an OpenAPI spec into MCP tools with Zilla
description: >-
  Compile an existing OpenAPI document into a governed MCP tool set that AI
  agents can call over Streamable HTTP, with one credential at the edge, OAuth
  identity on every tool call, and full telemetry — without writing an MCP
  server.
api: Zilla MCP Gateway
provider: Aklivity
generated: '2026-08-30'
method: generated
grounding: >-
  Binding names, kinds and behaviours are read from the Zilla 2.x reference and
  the AI-gateway guides. Aklivity hosts no MCP server of its own; the endpoint
  this skill produces belongs to whoever deploys it. See mcp/aklivity-mcp.yml.
operations:
  - binding: mcp (kind server)
  - binding: mcp (kind proxy)
  - binding: mcp (kind client)
  - binding: mcp-openapi (kind client)
  - binding: mcp-http (kind proxy)
  - binding: mcp-kafka (kind client)
  - guard: oauth
---

# Turn an OpenAPI spec into MCP tools with Zilla

## When to use this

You already maintain OpenAPI documents for your services and you want agents to
call them as MCP tools — without hand-authoring a tool list, standing up an MCP
server per service, or handing each agent a separate credential.

Reference: https://docs.aklivity.io/latest/ai-gateway/guides/openapi-specs-as-tools/

## How the pipeline is shaped

Zilla's MCP gateway is a chain of small bindings:

| Binding | Role |
| --- | --- |
| `mcp` · server | Terminates the inbound Streamable HTTP connection from the agent |
| `mcp` · proxy | Routes tool calls to upstreams by toolkit name |
| `mcp` · client | Connects to an upstream MCP server over HTTP, WebSocket or SSE |
| `mcp-http` · proxy | Exposes any HTTP API as MCP tools with no upstream MCP server |
| `mcp-openapi` · client | Compiles an OpenAPI document into a tool set |
| `mcp-kafka`, `mcp-kafka-connect`, `mcp-schema-registry` · client | Connect straight to the backend with a built-in or compiled tool set |

Reference: https://docs.aklivity.io/latest/ai-gateway/mcp-gateway/how-it-works/

## Steps

1. **Point an `mcp-openapi` client binding at your OpenAPI document.** The tool
   set is compiled from the spec — each operation becomes a tool, and the
   operation's parameters and request body become the tool's input schema. There
   is no hand-written tool list to drift.

   Reference: https://docs.aklivity.io/latest/reference/2.x/config/bindings/mcp-openapi/client.html

2. **Reshape the compiled tool set with an overlay** if the raw operation names
   or descriptions read badly to a model. Zilla supports an OpenAPI overlay on
   the MCP path specifically for this.

   Reference: https://docs.aklivity.io/latest/ai-gateway/mcp-gateway/openapi-overlay/

3. **Aggregate more than one upstream behind a single endpoint.** Put an
   `mcp` · proxy in front and give each exit a toolkit name; the proxy routes on
   the toolkit prefix carried by each tool call. The agent holds one URL and one
   credential no matter how many upstreams sit behind it.

   References:
   https://docs.aklivity.io/latest/ai-gateway/mcp-gateway/toolkit-routing/ and
   https://docs.aklivity.io/latest/ai-gateway/mcp-gateway/multi-server-aggregation/

4. **Let the listing cache answer discovery.** `tools/list`, `prompts/list` and
   `resources/list` are served by the cache layer in `mcp` · proxy before any
   upstream is reached, so agent discovery does not fan out to every backend.

   Reference: https://docs.aklivity.io/latest/ai-gateway/mcp-gateway/listing-cache/

5. **Put a guard in front.** The OAuth guard supports client credentials for
   machine-to-machine, RFC 7523 jwt-bearer, and RFC 8693 token exchange —
   token exchange is the one that carries the END USER's identity through to the
   upstream call rather than collapsing everyone into one service account.
   Per-user identity on every tool call is a Plus/Enterprise capability.

   Reference: https://docs.aklivity.io/latest/ai-gateway/security/oauth-guard/

6. **Watch it.** MCP session lifecycle and failures are named telemetry events:
   `BINDING_MCP_SESSION_ESTABLISHED`, `BINDING_MCP_SESSION_CLOSED`,
   `BINDING_MCP_AUTHORIZATION_FAILED`, `BINDING_MCP_ELICITATION_TIMEOUT`. Export
   them via `stdout`, `syslog`, `otlp`, `prometheus` or `aws-cloudwatch`. The
   full catalog is in `errors/aklivity-event-codes.yml`.

   Reference: https://docs.aklivity.io/latest/ai-gateway/guides/observable-ai-agents/

## What is free and what is not

Community (free, source-available) covers the MCP gateway, spec-driven tools
from OpenAPI, and tool discovery. Per-user identity on every tool call, semantic
tool search, auto-sized eager tool sets and MCP sessions served across a
multi-node cluster are Plus or Enterprise.

Reference: https://www.aklivity.io/pricing

## What this skill will not tell you

The tool names your spec produces. They are a function of YOUR OpenAPI document,
which this catalog has never seen. Compile it and call `tools/list` against your
own endpoint to find out — do not assume a naming convention.
