# SENTINEL Architecture - Guided Tour

This document provides a guided tour of the SENTINEL codebase at `D:\Projects\mercenary`. For the authoritative architecture, see `D:\Projects\mercenary\docs\engineering\ARCHITECTURE.md`.

## High-Level Request Flow

```
Client
  → SecurityFilter + RateLimitFilter
  → Controllers (MercenaryController, AdminController, etc.)
  → RagOrchestrationService
  → RAG services (HybridRAG, HiFi-RAG, Agentic, etc.)
  → VectorStore (LocalMongoVectorStore or MongoDB Atlas)
  → EmbeddingModel + ChatClient (Ollama / OpenAI / Anthropic / Vertex)
  → Response + audit
```

## Package Structure

| Package | Purpose | Key Classes |
|---------|---------|-------------|
| `controller` | HTTP endpoints | MercenaryController, AdminController, OidcBrowserFlowController, HyperGraphController |
| `service` | Orchestration, ingestion, audit | RagOrchestrationService, SecureIngestionService, AuditService, DemoDataService |
| `rag/hybridrag` | Hybrid semantic + keyword retrieval | HybridRagService, QueryExpander, LexicalIntentDetector |
| `rag/hifirag` | Reranking, ColBERT, cross-encoder | HiFiRagService, CrossEncoderReranker, RerankerSidecarClient |
| `rag/speculativerag` | Speculative RAG pipeline | SpeculativeRagService |
| `rag/agentic` | Agentic multi-hop reasoning | AgenticRagOrchestrator |
| `rag/megarag` | Multimodal (text + images) | MegaRagService, ImageAnalyzer |
| `rag/miarag` | MiA-RAG strategy | MiARagService |
| `rag/ragpart` | Corpus poisoning defense | RagPartService, PartitionAssigner |
| `rag/hgmem` | HyperGraph memory | HyperGraphMemory, GraphQualityScorer |
| `rag/router` | Query routing | RoutePolicy, RouteFeatureExtractor |
| `vector` | Vector store, embeddings | LocalMongoVectorStore (custom for local MongoDB), FilterExpressionEvaluator |
| `config` | Spring configuration | SecurityConfig, SectorConfig, RagPerformanceConfig |
| `security` | Auth, clearance, guards | RequestExecutionContext, ToolPermissionGuard, ContentSanitizer |
| `enterprise` | Edition-specific features | AdminController, HybridSearchService, SparseEmbeddingService |
| `connectors` | S3, SharePoint, Confluence | S3Connector, SharePointConnector, ConnectorService |
| `filter` | Request filters | SecurityFilter, CorrelationIdFilter, WorkspaceFilter |
| `observability` | Tracing, metrics | RagPipelineTracer, TracingConfig |

## Entry Points

### Main Application
- **MercenaryApplication.java** – Boot class, VectorStore bean, security validation on startup

### REST API
- **MercenaryController** – `/api/ask`, `/api/ask/stream`, `/api/ingest`, etc.
- **AdminController** (enterprise) – Admin dashboard, connectors, demo data

### Configuration
- **application.yaml** – Base config, MongoDB, Ollama, Spring AI
- **application-enterprise.yaml**, **application-foundation.yaml**, **application-frontier.yaml** – Profile-specific overrides

## Build & Editions

- **build.gradle** – Editions: `trial`, `enterprise`, `medical`, `government`
- Run with `-Pedition=enterprise` to build enterprise edition
- Edition exclusions control which packages are compiled (e.g., medical excludes government-only code)

## Data Flow

1. **Ingestion:** SecureIngestionService → PDF/Office/text extraction → chunks → embeddings → VectorStore
2. **Query:** User question → RagOrchestrationService → route to RAG strategy → retrieve chunks → LLM generation → response + citations
3. **Security:** RequestExecutionContext carries user, clearance, sectors; filters enforce before controllers

## Where to Look Next

- **Add a new RAG strategy:** `rag/` package, implement interface used by RagOrchestrationService
- **Change auth:** `config/SecurityConfig`, `security/` package
- **Tune retrieval:** `application.yaml` feature flags, `RagPerformanceConfig`
- **Add a connector:** `connectors/` package, `ConnectorService`
