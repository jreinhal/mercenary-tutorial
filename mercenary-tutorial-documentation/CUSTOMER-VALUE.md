# SENTINEL — Customer Value & Talking Points

Use this guide to explain SENTINEL to potential customers. Each feature is mapped to a customer benefit and a concise talking point.

---

## Core Value Proposition

**SENTINEL is a secure, air-gap compatible RAG platform for enterprise and government.** It lets organizations deploy AI-powered document Q&A on-premise, with full control over data, no cloud dependency, and compliance-ready security.

---

## RAG Strategies — "Why do I need multiple?"

| Feature | Customer Benefit | Talking Point |
|--------|------------------|----------------|
| **HybridRAG** | Best of semantic + keyword search | "We combine AI understanding with exact keyword matching—so you find documents whether users ask in natural language or use specific IDs, part numbers, or codes." |
| **HiFi-RAG** | Higher accuracy when it matters | "Reranking with cross-encoders improves precision for high-stakes queries—medical, legal, compliance—where wrong answers are costly." |
| **MegaRAG** | Use charts, diagrams, images | "We don't just index text. Charts, diagrams, and scanned images are analyzed and searchable—critical for technical and operational docs." |
| **Agentic** | Complex, multi-step questions | "For questions that need follow-up—'find the contract, then summarize the liability section'—our agentic mode chains retrieval steps automatically." |
| **RAGPart** | Defense against poisoned data | "If someone injects misleading content into your corpus, RAGPart partitions and validates before generation, reducing the risk of manipulated answers." |
| **CRAG** | Self-correcting retrieval | "When initial search returns weak results, CRAG rewrites the query and searches again—improving recall without manual retries." |
| **QuCo-RAG** | Hallucination awareness | "We quantify uncertainty. When the corpus doesn't support an answer, we flag it instead of guessing—critical for audit and compliance." |
| **AdaptiveRAG** | Right strategy per query | "Simple questions get fast, chunk-level retrieval. Complex ones get document-level or agentic—we route automatically." |

---

## Search Intelligence

| Feature | Customer Benefit | Talking Point |
|--------|------------------|----------------|
| **Query expansion** | Better recall | "We expand queries with synonyms and reformulations so users don't have to guess the exact wording in your documents." |
| **Domain thesaurus** | Industry terminology | "Acronyms and jargon are expanded per department—IT, legal, medical—so specialized vocabularies are handled correctly." |
| **Temporal filtering** | Time-aware answers | "When users ask 'what changed in 2024?', we filter retrieval by time—no mixing of outdated and current content." |

---

## Document Processing

| Feature | Customer Benefit | Talking Point |
|--------|------------------|----------------|
| **Table extraction** | Tables stay tables | "Tables in PDFs are extracted and indexed as structured data—not mangled text—so financials, specs, and schedules remain accurate." |
| **Metadata preservation** | Traceability | "Every chunk carries source, page number, and chunk index—full audit trail for citations and compliance." |
| **Multimodal ingestion** | Images, charts, scans | "We handle text, tables, and visual assets in one pipeline—no separate tools for different file types." |
| **Ingestion resilience** | Large corpora | "Checkpoint/resume and retries mean long ingestion runs complete reliably—even across millions of pages." |
| **Connectors** | S3, SharePoint, Confluence | "Sync directly from your existing content stores—no manual uploads, incremental updates only." |

---

## Security & Compliance

| Feature | Customer Benefit | Talking Point |
|--------|------------------|----------------|
| **Air-gap compatible** | No cloud, no data leave | "Runs entirely on-premise. LLM inference via Ollama—no data sent to external APIs." |
| **PII redaction** | NIST, GDPR, HIPAA aligned | "Automatic detection and redaction of PII in queries and responses—configurable by deployment." |
| **HIPAA strict mode** | Medical/healthcare | "Strict citation requirements, evidence excerpts, ephemeral visual evidence—no persistent image storage." |
| **Workspace isolation** | Multi-tenant | "Department and workspace-level isolation—users only see documents they're authorized for." |
| **Prompt injection detection** | Security | "Incoming queries are screened for injection attempts; detections are audit-logged." |
| **Auth modes** | OIDC, CAC | "Enterprise SSO via OIDC; CAC/smart card for government and classified environments." |
| **Editions** | Trial, Enterprise, Medical, Government | "Right feature set and compliance posture per sector—medical gets HIPAA, government gets classified-environment controls." |

---

## Trust & Citations

| Feature | Customer Benefit | Talking Point |
|--------|------------------|----------------|
| **Evidence metadata** | Source traceability | "Every answer cites source and page—users can verify, auditors can trace." |
| **Visual evidence** | Page and region rendering | "We can render the exact page and highlighted region—direct citation verification." |
| **Streaming parity** | Same guardrails | "Streaming responses enforce the same security and compliance as non-streaming—no shortcuts." |

---

## Quick Pitch (30 seconds)

"SENTINEL is an on-premise RAG platform for enterprise and government. It ingests your documents—PDFs, Office, images—and lets users ask questions in natural language. Answers are grounded in your corpus with citations. We support multiple retrieval strategies, multimodal content, and compliance features like PII redaction and HIPAA strict mode. It runs entirely on your infrastructure with Ollama—no data leaves your network."

---

## Reference

- **Full SENTINEL:** `D:\Projects\mercenary`
- **README:** `D:\Projects\mercenary\README.md`
- **RAG features:** `D:\Projects\mercenary\docs\engineering\RAG_FEATURES.md`
