# Glossary — Key Concepts & Technologies

Definitions for terms used in the SENTINEL tutorial and codebase.

---

## Transformers (Hugging Face)

**What it is:** The Hugging Face Python library for loading and running transformer models (BERT, GPT, etc.) and their tokenizers. It provides a standard API for model loading, tokenization, and inference.

**Why it matters for SENTINEL:** SENTINEL's optional Python sidecars use Transformers to run specialized models that aren't available in Ollama or Spring AI out of the box—for example:
- **Cross-encoder rerankers** — Score query–document pairs for relevance
- **ColBERT** — Late-interaction reranking (MaxSim scoring)
- **Sparse embedding models** — BGE-M3 learned sparse weights for hybrid retrieval

**Key idea:** The main SENTINEL app is Java. Python + Transformers runs in separate sidecar processes. The Java app calls them over HTTP when those features are enabled.

**Learn more:** [huggingface.co/docs/transformers](https://huggingface.co/docs/transformers)

---

## Sidecars

**What it is:** A **sidecar** is a separate process or service that runs alongside the main application and provides specialized functionality. The main app delegates certain tasks to the sidecar instead of doing them itself.

**Why SENTINEL uses sidecars:**
- **Language split:** The main app is Java/Spring. Some AI models and libraries (e.g., Hugging Face Transformers) are Python-native. Rather than embedding Python in Java, SENTINEL runs Python services as sidecars.
- **Resource isolation:** Sidecars can run on CPU while Ollama uses GPU, or vice versa—no conflict.
- **Optional features:** Sidecars are optional. If a sidecar isn't running, SENTINEL falls back to other modes (e.g., keyword matching instead of sparse embeddings).

**SENTINEL sidecars:**

| Sidecar | Purpose | Port (default) |
|---------|---------|----------------|
| **reranker-sidecar** | Cross-encoder model for reranking retrieved chunks | — |
| **colbert-reranker-sidecar** | ColBERT v2 late-interaction reranking (MaxSim) | 8093 |
| **sparse-embedding-sidecar** | BGE-M3 learned sparse (lexical) weights for hybrid retrieval | 8091 |

**Flow:** Java app → HTTP request → Sidecar (Python) → Model inference (Transformers) → Response → Java app

**Key idea:** Think of a sidecar as a helper service. The main app says "rerank these 10 chunks" and the sidecar returns scores. The main app never loads the model itself.

---

## Other Terms

| Term | Definition |
|------|------------|
| **Ollama** | Local LLM runtime. Runs models (e.g., llama3.1, bge-m3) on your machine. No cloud. |
| **RAG** | Retrieval Augmented Generation. Retrieve relevant docs, then generate an answer grounded in them. |
| **Embedding** | A vector (list of numbers) that represents text. Similar text → similar vectors. |
| **Vector store** | Database that stores embeddings and supports similarity search. |
| **Reranking** | After initial retrieval, score candidates with a more accurate (but slower) model. |
| **BOM** | Bill of Materials. In Gradle, `dependencyManagement` imports a BOM to align dependency versions. |

---

## Reference

- **Full SENTINEL:** `D:\Projects\mercenary`
- **Sidecars:** `D:\Projects\mercenary\tools\` (sparse-embedding-sidecar, colbert-reranker-sidecar, reranker-sidecar)
