# Langflow

API Evangelist profile of [Langflow](https://www.langflow.org) — the open-source low-code visual builder for AI agents, RAG pipelines, and LangChain-based workflows.

Langflow pairs a drag-and-drop React Flow frontend with a FastAPI backend that exposes every flow as a REST API, an MCP server, and an OpenAI-compatible Responses endpoint. Components are editable Python and ship with integrations across most major LLMs, vector stores, and observability platforms.

Langflow was acquired by DataStax in 2025; IBM completed its acquisition of DataStax on **May 28, 2025**, making Langflow an IBM property while remaining MIT-licensed open source under the `langflow-ai` GitHub organization.

- **Project URL**: https://www.langflow.org
- **Documentation**: https://docs.langflow.org
- **GitHub**: https://github.com/langflow-ai/langflow
- **License**: MIT
- **Language**: Python (FastAPI) + TypeScript (React Flow)
- **Latest release**: v1.9.3 (2026-05-15)
- **Stars**: 149k+
- **Owner**: IBM (via DataStax)

## APIs

The Langflow REST API serves an OpenAPI 3.1 spec at `/openapi.json` on every deployment. We've grouped the 67 operations into 13 logical API surfaces:

| API | Description |
|---|---|
| [Langflow API](apis.yml) | Umbrella REST surface — FastAPI app at `/api/v1` and `/api/v2`. |
| [Flows API](apis.yml) | CRUD for flows, the canonical Langflow unit. |
| [Run API](apis.yml) | Execute a flow by id or name; simplified, advanced, and webhook variants. |
| [Build API](apis.yml) | Vertex-level streaming flow builds with job lifecycle. |
| [Projects API](apis.yml) | Group flows into projects; supports import/export and MCP installation. |
| [Files API](apis.yml) | Per-flow (v1) and per-user (v2) file storage with batch operations. |
| [Monitor API](apis.yml) | Sessions, chat messages, shared sessions, and vertex build logs. |
| [Traces API](apis.yml) | Execution traces with LangSmith / LangFuse integration. |
| [Users API](apis.yml) | User CRUD, whoami, and password reset. |
| [API Keys API](apis.yml) | Create, list, and rotate Langflow API keys. |
| [MCP API](apis.yml) | Manage global and per-project MCP servers. |
| [Workflow API](apis.yml) | v2 workflow execution and stop endpoints. |
| [OpenAI Responses API](apis.yml) | OpenAI-compatible Responses endpoint at `/api/v1/responses`. |

## Artifacts

| Type | Path | Notes |
|---|---|---|
| OpenAPI 3.1 spec | [`openapi/langflow-openapi.yml`](openapi/langflow-openapi.yml) | 67 paths, 87 schemas, generated from `docs/openapi/openapi.json` in the upstream repo. |
| Naftiko capabilities | [`capabilities/`](capabilities/) | 12 capability files — one per API surface — each exposing REST and MCP adapters. |
| JSON Schemas | [`json-schema/`](json-schema/) | Flow, Project, Message, User, MCP Server. |
| JSON Structure | [`json-structure/`](json-structure/) | Flow graph structure (nodes / edges / viewport). |
| JSON-LD context | [`json-ld/langflow-context.jsonld`](json-ld/langflow-context.jsonld) | Maps Langflow entities into schema.org and the Langflow vocab namespace. |
| Examples | [`examples/`](examples/) | Run, create, webhook, list MCP servers. |
| Spectral ruleset | [`rules/langflow-rules.yml`](rules/langflow-rules.yml) | Enforces Langflow API conventions. |
| Vocabulary | [`vocabulary/langflow-vocabulary.yml`](vocabulary/langflow-vocabulary.yml) | Operational + capability vocabulary across nine dimensions. |

## Authentication

All authenticated endpoints accept a Langflow API key via the `x-api-key` request header or the `x-api-key` query parameter:

```bash
curl -X POST "http://localhost:7860/api/v1/run/customer-support-agent?stream=false" \
  -H "x-api-key: $LANGFLOW_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"input_value": "What is the status of order 12345?"}'
```

API keys can be created via Settings → Langflow API Keys in the UI, or via the `langflow api-key` CLI when the frontend is disabled.

## Installation

```bash
# PyPI
uv pip install langflow -U
langflow run

# Docker
docker run -p 7860:7860 langflowai/langflow:latest

# Helm (Kubernetes)
helm repo add langflow https://langflow-ai.github.io/langflow-helm-charts
helm install langflow langflow/langflow
```

Desktop apps are available for macOS 13+ and Windows.

## Ownership

- **DataStax** acquired Langflow in 2025.
- **IBM** announced the acquisition of DataStax on **2025-02-25** and closed the deal on **2025-05-28**.
- Langflow itself remains **MIT-licensed open source** under the [`langflow-ai`](https://github.com/langflow-ai) GitHub organization.
- A hosted **Langflow Cloud** option is operated by DataStax / IBM.

## Related repositories in langflow-ai

| Repo | Purpose |
|---|---|
| [langflow](https://github.com/langflow-ai/langflow) | Main project. |
| [langflow-helm-charts](https://github.com/langflow-ai/langflow-helm-charts) | Helm charts for Kubernetes deployment. |
| [langflow-embedded-chat](https://github.com/langflow-ai/langflow-embedded-chat) | Embeddable chat web component. |
| [langflow-client-ts](https://github.com/langflow-ai/langflow-client-ts) | TypeScript client for the Langflow API. |
| [langflow-railway](https://github.com/langflow-ai/langflow-railway) | Railway deploy template. |
| [openrag](https://github.com/langflow-ai/openrag) | Single-package RAG platform built on Langflow + Docling + OpenSearch. |
| [mcp-sse-shim](https://github.com/langflow-ai/mcp-sse-shim) | MCP SSE compatibility shim. |
| [langflow-bundles](https://github.com/langflow-ai/langflow-bundles) | Pre-packaged component bundles. |
| [langflow-twilio-voice](https://github.com/langflow-ai/langflow-twilio-voice) | Twilio ConversationRelay + Langflow voice agent example. |

## About

Profile maintained by [Kin Lane](https://apievangelist.com), the API Evangelist. Part of the [API Evangelist network](https://github.com/api-evangelist).
