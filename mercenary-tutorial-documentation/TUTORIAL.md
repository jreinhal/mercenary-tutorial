# SENTINEL Intelligence Platform - Tutorial & Guide

Welcome! This tutorial helps you understand and work with the SENTINEL Intelligence Platform. SENTINEL is a secure, air-gap compatible RAG (Retrieval Augmented Generation) platform for enterprise and government deployments.

**Tutorial project:** `d:\Tutorials\mercenary\mercenary-tutorial` (scaffold we build step-by-step)  
**Tutorial docs:** `d:\Tutorials\mercenary\mercenary-tutorial-documentation`  
**Full SENTINEL reference:** `D:\Projects\mercenary` (production codebase)

**Structure:** `mercenary\` contains `mercenary-tutorial\` (code) and `mercenary-tutorial-documentation\` (docs)

**Customer focus:** See **CUSTOMER-VALUE.md** for feature-to-benefit mapping and talking points when explaining SENTINEL to customers.

**Unfamiliar terms?** See **GLOSSARY.md** for definitions (Transformers, sidecars, RAG, embeddings, etc.).

## How to Read This Tutorial

| Term | Meaning |
|------|---------|
| **Prerequisites** | What you need *before* starting (e.g., Java installed) |
| **Step** | A phase of the tutorial—a milestone with a goal (Step 1, 2, 3…) |
| **Instructions** | The numbered list of *what to do* inside each step |

**Step** = the phase (e.g., "Run the Application"). **Instructions** = the how-to (e.g., "1. Open terminal. 2. Run this command.").

---

## How This Tutorial Works

Each step includes:
- **Instructions** – What to do
- **Context** – How the codebase is structured and why
- **Verification** – How to confirm things work

We build understanding by working with the tutorial scaffold. The full SENTINEL project is available as reference.

## Learning Objectives

By the end of this tutorial, you will:
1. Understand the SENTINEL architecture and module layout
2. Run the application locally with MongoDB and Ollama
3. Navigate the codebase effectively in Cursor
4. Know where key features live (RAG, security, ingestion, etc.)
5. Use the project's documentation for deeper dives

## Prerequisites

Before starting, ensure you have:
- **Java 21 (LTS)** installed
- **Git** installed
- **Cursor IDE** installed

*MongoDB and Ollama are needed later when we add RAG features. The early steps run without them.*

## Project Overview

SENTINEL is a mature, production-ready platform. Key capabilities include:

| Area | Features |
|------|----------|
| **RAG** | HybridRAG, HiFi-RAG, MegaRAG, MiA-RAG, Agentic, Speculative, RAGPart, CRAG |
| **Retrieval** | Semantic + keyword fusion, query expansion, reranking, temporal filtering |
| **Ingestion** | PDF, Office, text; table extraction; S3/SharePoint/Confluence connectors |
| **Security** | DEV, STANDARD, OIDC, CAC auth; clearance levels; audit logging |
| **Editions** | trial, enterprise, medical, government (build-time selection) |

**Stack:** Spring Boot 3.4, Spring AI, MongoDB, Ollama (local) / OpenAI / Anthropic / Vertex AI (cloud profiles).

## Tutorial Structure

**Goal:** Build a SENTINEL clone step-by-step. See **ROADMAP.md** for the full plan.

- **Step 0:** Generate project with Spring Initializr (optional—if starting from scratch)
- **Steps 0–4:** Foundation ✓
- **Steps 5–55:** Full clone (see ROADMAP.md) — build & config, security, vector store, ingestion, basic RAG, advanced RAG strategies, search intelligence, connectors, trust & compliance, UI

---

## Step 0: Generate the Project (Optional)

**Use this step only if you don't have the scaffold.** If you already have `d:\Tutorials\mercenary\mercenary-tutorial`, skip to Step 1.

**Instructions:**
1. Go to **https://start.spring.io**
2. Configure: Gradle, Java, Spring Boot 3.4.x, Group `com.jreinhal`, Artifact `mercenary`, Java 21
3. Add dependencies: Spring Web, Spring Data MongoDB, Spring Boot DevTools
4. Click **Generate**, extract the ZIP to `d:\Tutorials\`
5. Open the `mercenary` folder in Cursor

See **STEP-00.md** for detailed instructions.

---

## Step 1: Open the Project

**Instructions:**
Open the tutorial project in Cursor and verify the structure.

**Instructions:**
1. In Cursor: **File → Open Folder** (or `Ctrl+K Ctrl+O`)
2. Navigate to `d:\Tutorials\mercenary\mercenary-tutorial`
3. Click **Select Folder**

**What you'll see:**
- `build.gradle` – Spring Boot, Spring Web (or WebMVC), Spring Data MongoDB, DevTools
- `src/main/java/com/jreinhal/mercenary/MercenaryApplication.java` – Main application class
- `src/main/resources/application.properties` – Configuration (MongoDB disabled for now)

**Verification:**
- File explorer shows the structure above
- `MercenaryApplication.java` exists and has `@SpringBootApplication`
- `build.gradle` lists Spring Web, Spring Data MongoDB

See **STEP-01.md** for detailed exploration and verification steps.

---

## Step 2: Run the Application

**Instructions:**
Run the tutorial scaffold. No MongoDB or Ollama needed—MongoDB is disabled in config.

**Instructions:**
1. In the terminal (`Ctrl+` `), from the project root (`d:\Tutorials\mercenary\mercenary-tutorial`):
   ```powershell
   .\gradlew bootRun
   ```
2. Wait for "Started MercenaryApplication"
3. Press `Ctrl+C` to stop

**Verification:**
- App starts without errors
- "Started MercenaryApplication" appears in logs

See **STEP-02.md** for step-by-step instructions. A "Full SENTINEL" path is also documented if you want to run the production app.

---

## Step 3: Explore the Architecture

**Instructions:**
Understand where key features live in the codebase.

**Key packages:**
- `controller` – HTTP endpoints (MercenaryController, AdminController, etc.)
- `service` – RagOrchestrationService, SecureIngestionService, etc.
- `rag/` – hybridrag, hifirag, speculativerag, agentic, megarag, miarag
- `config` – SecurityConfig, SectorConfig, RagPerformanceConfig
- `security` – Auth, clearance, RequestExecutionContext
- `vector` – LocalMongoVectorStore, FilterExpressionEvaluator

**Documentation:**
- `D:\Projects\mercenary\README.md` – Quick start, capabilities, config
- `D:\Projects\mercenary\docs\engineering\ARCHITECTURE.md` – Runtime flow, modules
- `D:\Projects\mercenary\docs\engineering\DEVELOPMENT.md` – Build, run, test
- `D:\Projects\mercenary\docs\engineering\CONFIGURATION.md` – Env vars, feature flags

See **ARCHITECTURE.md** in this tutorial folder for a guided tour.

---

## Progress Tracker

- [ ] Step 0: Generate project with Spring Initializr (optional)
- [x] Step 1: Open project and verify structure
- [x] Step 2: Run the application
- [x] Step 3: Explore the architecture
- [x] Step 4: Make a small change
- [ ] Step 5: Add dependencies (Lombok, Security, Spring AI)
- [ ] Step 6: Create application.yaml
- [ ] Step 7: Enable MongoDB
- [ ] … (see ROADMAP.md)

---

---

## Step 5: Add Dependencies

**Instructions:**
Add Lombok, Spring Security, and Spring AI (Ollama) to `build.gradle`. See **STEP-05.md** for detailed instructions.

**Summary:** Update Spring Boot to 3.4.13, add milestone repo, add Lombok + Security + Spring AI Ollama, add dependencyManagement for Spring AI BOM. Run `.\gradlew build` to verify.

---

## Cursor IDE Tips

### Basic Navigation
- **File Explorer**: `Ctrl+Shift+E`
- **Search**: `Ctrl+Shift+F` to search across files
- **Quick file open**: `Ctrl+P` then type filename
- **Terminal**: `Ctrl+` ` (backtick)

### AI Features
- **Chat**: `Ctrl+L` to open AI chat
- **Composer**: `Ctrl+I` for inline AI assistance
- **Code Actions**: Right-click on code for AI suggestions

### Project-Specific
- Use `Ctrl+P` and type `MercenaryController` or `RagOrchestrationService` to jump to key files
- Search for `@RestController` or `@Service` to find endpoints and services
