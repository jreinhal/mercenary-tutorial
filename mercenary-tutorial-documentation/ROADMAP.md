# SENTINEL Clone — Full Roadmap (Option C)

**Goal:** Build and understand the complete SENTINEL platform so you can explain it to customers. Each step is beginner-friendly and builds on the previous.

**Customer focus:** See **CUSTOMER-VALUE.md** for feature-to-benefit mapping and talking points.

---

## Phase 1: Foundation ✓

| Step | Goal | Status |
|------|------|--------|
| 0 | Generate project with Spring Initializr (optional) | — |
| 1 | Open project, verify structure | ✓ |
| 2 | Run application | ✓ |
| 3 | Explore architecture | ✓ |
| 4 | Add HomeController | ✓ |

---

## Phase 2: Build & Configuration (Steps 5–7)

| Step | Goal |
|------|------|
| 5 | Add dependencies (Lombok, Security, Spring AI Ollama) |
| 6 | Create application.yaml, migrate from properties |
| 7 | Enable MongoDB, configure connection |

---

## Phase 3: Security Basics (Steps 8–11)

| Step | Goal |
|------|------|
| 8 | Add SecurityConfig (dev mode, permit / and /api) |
| 9 | Add auth context, request scoping |
| 10 | Workspace/department isolation |
| 11 | PII redaction (NIST, GDPR, HIPAA alignment) |

---

## Phase 4: Vector Store & Embeddings (Steps 12–15)

| Step | Goal |
|------|------|
| 12 | Add vector store (LocalMongoVectorStore or Spring AI) |
| 13 | Configure Ollama embedding model |
| 14 | Add VectorStore bean |
| 15 | Sparse embeddings (optional BGE-M3 learned sparse) |

---

## Phase 5: Document Ingestion (Steps 16–22)

| Step | Goal |
|------|------|
| 16 | Document reader (PDF, text) |
| 17 | Ingestion service, chunking |
| 18 | /api/ingest endpoint |
| 19 | Table-aware extraction (Tabula) |
| 20 | Metadata preservation (page_number, chunk_index) |
| 21 | Multimodal visual analysis (MegaRAG image pipeline) |
| 22 | Ingestion resilience (checkpoint/resume) |

---

## Phase 6: Basic RAG (Steps 23–26)

| Step | Goal |
|------|------|
| 23 | RAG service (retrieve + LLM generate) |
| 24 | /api/ask endpoint |
| 25 | Streaming /api/ask/stream |
| 26 | Citations and evidence metadata |

---

## Phase 7: Advanced RAG Strategies (Steps 27–38)

| Step | Goal |
|------|------|
| 27 | HybridRAG — semantic + keyword fusion, RRF |
| 28 | Query expansion (deterministic + LLM-assisted) |
| 29 | AdaptiveRAG — query routing (chunk vs document) |
| 30 | HiFi-RAG — reranking, ColBERT, cross-encoder |
| 31 | CRAG — corrective retrieval (low-confidence rewrite) |
| 32 | QuCo-RAG — uncertainty quantification, hallucination checks |
| 33 | RAGPart — corpus poisoning defense |
| 34 | MegaRAG — multimodal (charts, diagrams, images) |
| 35 | MiA-RAG — MiA retrieval strategy |
| 36 | BidirectionalRAG |
| 37 | Agentic orchestrator — multi-hop reasoning, tools |
| 38 | HGMem (HyperGraph memory), Self-RAG, HyDE (optional) |

---

## Phase 8: Search Intelligence (Steps 39–42)

| Step | Goal |
|------|------|
| 39 | Domain thesaurus (acronyms, synonyms) |
| 40 | Temporal filtering |
| 41 | OCR-tolerance heuristics (degraded scans) |
| 42 | Feature flags, strategy selection |

---

## Phase 9: Connectors & Sync (Steps 43–46)

| Step | Goal |
|------|------|
| 43 | S3 connector |
| 44 | SharePoint connector |
| 45 | Confluence connector |
| 46 | Incremental sync, fingerprint tracking |

---

## Phase 10: Trust & Compliance (Steps 47–51)

| Step | Goal |
|------|------|
| 47 | Visual evidence endpoints (source page, region rendering) |
| 48 | Prompt injection detection, audit logging |
| 49 | HIPAA strict mode (medical edition) |
| 50 | License validation, editions (trial, enterprise, medical, government) |
| 51 | Auth modes (OIDC, CAC) |

---

## Phase 11: UI & Polish (Steps 52–55)

| Step | Goal |
|------|------|
| 52 | Chat UI (HTML/JS) |
| 53 | Admin dashboard |
| 54 | Health endpoint, observability |
| 55 | Documentation, runbooks |

---

## Summary

| Phase | Steps | Focus |
|-------|-------|-------|
| 1 | 0–4 | Foundation ✓ |
| 2 | 5–7 | Build & config |
| 3 | 8–11 | Security |
| 4 | 12–15 | Vector store |
| 5 | 16–22 | Document ingestion |
| 6 | 23–26 | Basic RAG |
| 7 | 27–38 | Advanced RAG strategies |
| 8 | 39–42 | Search intelligence |
| 9 | 43–46 | Connectors |
| 10 | 47–51 | Trust & compliance |
| 11 | 52–55 | UI & polish |

**Total: ~55 steps**

---

## Reference

- **Full SENTINEL:** `D:\Projects\mercenary`
- **Tutorial scaffold:** `d:\Tutorials\mercenary\mercenary-tutorial`
- **Customer value:** See CUSTOMER-VALUE.md
- **Architecture:** See ARCHITECTURE.md
