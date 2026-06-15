# Langflow (langflow)

Langflow is an open-source low-code visual builder for AI agents, RAG pipelines, and LangChain-based workflows. It pairs a drag-and-drop React Flow frontend with a FastAPI backend that exposes every flow as a REST API, an MCP server, and an OpenAI-compatible Responses endpoint. Components are editable Python and ship with integrations across most major LLMs, vector stores, and observability platforms. Langflow was acquired by DataStax in 2025; DataStax itself was acquired by IBM and the deal closed on May 28, 2025, making Langflow an IBM property while remaining MIT-licensed open source. The project is the canonical reference implementation for visually composing LangChain agents — 149k+ GitHub stars, distributed via PyPI, Docker, Helm, and native Desktop apps, with a hosted cloud option run by DataStax.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/langflow/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/langflow/refs/heads/main/apis.yml)

## Scope

- **Position:** Producing
- **Access:** 3rd-Party

## Tags

- AI
- Artificial Intelligence
- Agents
- Workflows
- Low-Code
- Visual Builder
- LangChain
- RAG
- MCP
- Open Source
- FastAPI

## Timestamps

- **Created:** 2026-05-24T00:00:00.000Z
- **Modified:** 2026-05-24

## APIs

### Langflow API

Langflow's FastAPI-based REST API exposes every capability of a running Langflow server — running flows, building flows, managing projects, files, users, API keys, MCP servers, messages and sessions, traces, starter projects, and an OpenAI-compatible Responses endpoint. Authentication is via the `x-api-key` header or query parameter. An interactive OpenAPI 3.1 spec is served at `/docs` and `/openapi.json` on every deployment.

- **Human URL:** [https://docs.langflow.org/api-reference-api-examples](https://docs.langflow.org/api-reference-api-examples)
- **Base URL:** `http://localhost:7860/api`

#### Tags

- AI
- Agents
- Workflows
- Low-Code
- LangChain

#### Properties

- [Documentation](https://docs.langflow.org/api-reference-api-examples)
- [Authentication](https://docs.langflow.org/api-keys-and-authentication)
- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON-LD](json-ld/langflow-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](vocabulary/langflow-vocabulary.yml)
- [Spectral Ruleset](rules/langflow-rules.yml)

### Langflow Flows API

Create, read, update, delete, upload, download, and list flows. A flow is the canonical Langflow unit — a directed graph of components representing an AI agent or workflow. Includes endpoints for batch creation, basic examples, public flows, and starter projects.

- **Human URL:** [https://docs.langflow.org/concepts-flows](https://docs.langflow.org/concepts-flows)

#### Tags

- AI
- Flows
- Agents

#### Properties

- [Documentation](https://docs.langflow.org/concepts-flows)
- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/langflow-flow-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Langflow Run API

Execute a flow by id or name via POST `/api/v1/run/{flow_id_or_name}` (simplified), POST `/api/v1/run/advanced/{flow_id_or_name}` (experimental advanced), or POST `/api/v1/webhook/{flow_id_or_name}` for webhook-triggered runs. Returns flow outputs and supports streaming via the `stream` query parameter.

- **Human URL:** [https://docs.langflow.org/api-reference-api-examples](https://docs.langflow.org/api-reference-api-examples)

#### Tags

- AI
- Agents
- Execution

#### Properties

- [Documentation](https://docs.langflow.org/api-reference-api-examples)
- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Langflow Build API

Build endpoints run a flow with full vertex-level streaming. POST `/api/v1/build/{flow_id}/flow` kicks off a build job and returns a job id; GET `/api/v1/build/{job_id}/events` streams vertex build events; POST `/api/v1/build/{job_id}/cancel` cancels in-flight builds. Public-tmp variants exist for unauthenticated public flow execution.

- **Human URL:** [https://docs.langflow.org/api-reference-api-examples](https://docs.langflow.org/api-reference-api-examples)

#### Tags

- AI
- Build
- Streaming

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Langflow Projects API

Create, list, read, update, delete, upload, and download Langflow projects. Projects are containers that group flows and provide MCP server installation context.

- **Human URL:** [https://docs.langflow.org/concepts-flows-import](https://docs.langflow.org/concepts-flows-import)

#### Tags

- AI
- Projects
- Organization

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/langflow-project-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Langflow Files API

Upload, download, list, and delete files attached to a flow (v1) or to the authenticated user (v2). The v2 Files API supports batch upload/download, batch delete, and profile-picture management.

- **Human URL:** [https://docs.langflow.org/concepts-file-management](https://docs.langflow.org/concepts-file-management)

#### Tags

- AI
- Files
- Storage

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Langflow Monitor API

Inspect and manage execution history — vertex builds, chat messages, sessions, and shared sessions. Supports listing, updating, renaming, and deleting messages and entire sessions, plus shared-session sharing for read-only collaboration.

- **Human URL:** [https://docs.langflow.org/concepts-flows-monitor](https://docs.langflow.org/concepts-flows-monitor)

#### Tags

- AI
- Monitoring
- Messages
- Sessions

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/langflow-message-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Langflow Traces API

Retrieve and delete execution traces. GET `/api/v1/monitor/traces` lists traces with flow-id filtering; GET `/api/v1/monitor/traces/{trace_id}` returns a single trace. Integrates with external observability providers like LangSmith and LangFuse.

- **Human URL:** [https://docs.langflow.org/concepts-flows-monitor](https://docs.langflow.org/concepts-flows-monitor)

#### Tags

- AI
- Tracing
- Observability

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Langflow Users API

User management endpoints — create, read, patch, and delete users; `/api/v1/users/whoami` returns the current authenticated user; reset-password endpoint for superuser-driven credential resets.

- **Human URL:** [https://docs.langflow.org/configuration-authentication](https://docs.langflow.org/configuration-authentication)

#### Tags

- AI
- Users
- Administration

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/langflow-user-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Langflow MCP API

Manage MCP (Model Context Protocol) servers attached to Langflow projects and globally. Every Langflow project can be exposed as an MCP server so its flows are callable as MCP tools. Endpoints list, register, update, and remove MCP servers, and install MCP configurations into Claude Desktop and other MCP hosts.

- **Human URL:** [https://docs.langflow.org/mcp-server](https://docs.langflow.org/mcp-server)

#### Tags

- AI
- MCP
- Model Context Protocol
- Servers

#### Properties

- [Documentation](https://docs.langflow.org/mcp-server)
- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/langflow-mcp-server-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Langflow Workflow API

v2 Workflow execution API — POST `/api/v2/workflows` executes a workflow; GET returns workflow status; POST `/api/v2/workflows/stop` halts a running workflow. The v2 workflow surface is the forward-looking execution interface for Langflow agents.

- **Human URL:** [https://docs.langflow.org/concepts-flows](https://docs.langflow.org/concepts-flows)

#### Tags

- AI
- Workflows
- Execution

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Langflow OpenAI Responses API

OpenAI-compatible Responses endpoint at POST `/api/v1/responses`. Lets clients written against OpenAI's Responses API point at a Langflow flow without code changes — the flow plays the role of the model and tool-calling layer.

- **Human URL:** [https://docs.langflow.org/api-reference-api-examples](https://docs.langflow.org/api-reference-api-examples)

#### Tags

- AI
- OpenAI-Compatible
- Responses

#### Properties

- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Langflow API Keys API

Create, list, rotate, and delete Langflow API keys. Keys authenticate requests against any of the Langflow REST endpoints via the `x-api-key` header. Also creatable via the `langflow api-key` CLI when the frontend is disabled.

- **Human URL:** [https://docs.langflow.org/api-keys-and-authentication](https://docs.langflow.org/api-keys-and-authentication)

#### Tags

- AI
- Authentication
- Administration

#### Properties

- [Documentation](https://docs.langflow.org/api-keys-and-authentication)
- [OpenAPI](openapi/langflow-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/langflow.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/langflow.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://www.langflow.org)
- [Documentation](https://docs.langflow.org)
- [Getting Started](https://docs.langflow.org/get-started-installation)
- [Getting Started](https://docs.langflow.org/get-started-quickstart)
- [Documentation](https://docs.langflow.org/api-reference-api-examples)
- [Authentication](https://docs.langflow.org/api-keys-and-authentication)
- [Documentation](https://docs.langflow.org/concepts-flows)
- [Documentation](https://docs.langflow.org/concepts-components)
- [Documentation](https://docs.langflow.org/configuration-authentication)
- [Documentation](https://docs.langflow.org/deployment-overview)
- [Documentation](https://docs.langflow.org/deployment-docker)
- [Documentation](https://docs.langflow.org/deployment-kubernetes)
- [Changelog](https://docs.langflow.org/release-notes)
- [Source Code](https://github.com/langflow-ai/langflow)
- [GitHub Organization](https://github.com/langflow-ai)
- [License](https://github.com/langflow-ai/langflow/blob/main/LICENSE)
- [Changelog](https://github.com/langflow-ai/langflow/releases)
- [Issue Tracker](https://github.com/langflow-ai/langflow/issues)
- [Documentation](https://github.com/langflow-ai/langflow/blob/main/CONTRIBUTING.md)
- [Helm Chart](https://github.com/langflow-ai/langflow-helm-charts)
- [Tool](https://github.com/langflow-ai/langflow-embedded-chat)
- [SDK](https://github.com/langflow-ai/langflow-client-ts)
- [Deployment](https://github.com/langflow-ai/langflow-railway)
- [Tool](https://github.com/langflow-ai/openrag)
- [Tool](https://github.com/langflow-ai/langflow-bundles)
- [Code Examples](https://github.com/langflow-ai/langflow-twilio-voice)
- [Tool](https://github.com/langflow-ai/mcp-sse-shim)
- [Package](https://pypi.org/project/langflow/)
- [Container](https://hub.docker.com/r/langflowai/langflow)
- [Documentation](https://docs.langflow.org/develop-application)
- [Documentation](https://docs.langflow.org/concepts-flows-import)
- [Documentation](https://docs.langflow.org/concepts-file-management)
- [Documentation](https://docs.langflow.org/concepts-flows-monitor)
- [Documentation](https://docs.langflow.org/concepts-publish)
- [Documentation](https://docs.langflow.org/concepts-playground)
- [Documentation](https://docs.langflow.org/agents-overview)
- [Documentation](https://docs.langflow.org/mcp-server)
- [Documentation](https://docs.langflow.org/mcp-client)
- [Documentation](https://docs.langflow.org/typescript-client)
- [Forum](https://discord.com/invite/EqksyE2EX9)
- [Video](https://www.youtube.com/@Langflow)
- [Twitter](https://twitter.com/langflow_ai)
- [LinkedIn](https://www.linkedin.com/company/langflow-ai/)
- [Blog](https://www.langflow.org/blog)
- [Use Cases](https://www.langflow.org/use-cases)
- [Newsletter](https://www.langflow.org/newsletter)
- [Owner](https://www.ibm.com/products/datastax)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
