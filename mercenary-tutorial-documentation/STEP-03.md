# Step 3: Explore the Architecture

## Objective
Understand the tutorial scaffold's current structure and the target architecture we're building toward. This step is exploratory—no code changes.

## Prerequisites
- Step 1 and Step 2 complete
- Tutorial scaffold open in Cursor

## Instructions

### 1. Explore the Scaffold (d:\Tutorials\mercenary\mercenary-tutorial)

In the file explorer, open and skim:

| File | What it does |
|------|--------------|
| `build.gradle` | Dependencies: Spring Boot, Web, MongoDB, DevTools |
| `MercenaryApplication.java` | Main class with `@SpringBootApplication` |
| `application.properties` | App name, MongoDB exclusion |

**Current state:** One main class, no controllers, no services. We'll add these in later steps.

### 2. Read the Architecture Guide

Open **ARCHITECTURE.md** (in this tutorial folder). It describes the full SENTINEL structure at `D:\Projects\mercenary`—the target we're building toward.

**Key concepts:**
- **Request flow:** Client → Controllers → Services → RAG → VectorStore → LLM
- **Packages:** controller, service, rag, config, security, vector
- **Entry points:** MercenaryController, RagOrchestrationService

### 3. (Optional) Browse Full SENTINEL

If you have `D:\Projects\mercenary` available:
- Open it in a new window or add to workspace
- Browse `src/main/java/com/jreinhal/mercenary/` to see the package structure
- Skim `MercenaryController.java` to see how endpoints are defined

## Verification

- [ ] You've looked at the scaffold's build.gradle, MercenaryApplication, application.properties
- [ ] You've read ARCHITECTURE.md
- [ ] You understand: scaffold is minimal now; we're building toward the full structure

## Ready to Continue?

Reply with **"Step 3 complete"** and I'll provide Step 4 (Make a small change—add a simple controller or endpoint).
