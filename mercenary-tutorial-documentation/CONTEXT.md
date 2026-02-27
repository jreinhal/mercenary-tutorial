# Conversation Context (Compact)

**Last updated:** 2026-02-23

*Updated automatically at natural break points. Paste into a new chat to restore context.*

## Project Setup
- **Tutorial scaffold (code):** `d:\Tutorials\mercenary\mercenary-tutorial` — Spring Boot, Spring Web, MongoDB (disabled), DevTools; runs on port 8081
- **Tutorial docs:** `d:\Tutorials\mercenary\mercenary-tutorial-documentation` — TUTORIAL.md, STEP-00–05, ROADMAP.md, CUSTOMER-VALUE.md, ARCHITECTURE.md, CURSOR-GUIDE.md
- **Full SENTINEL:** `D:\Projects\mercenary` — Production codebase (reference only; user runs tutorial scaffold)

## Tutorial Progress
- [x] Step 1: Open project, verify structure
- [x] Step 2: Run application — `.\gradlew bootRun`; app starts; 80% EXECUTING normal; Whitelabel 404 at / expected
- [x] Step 3: Explore architecture
- [x] Step 4: Make a small change — HomeController added; app serves welcome message at http://localhost:8081

## Key Decisions
- **User creates code** — Tutorial gives instructions; user creates files/classes (no pre-creation)
- User runs **tutorial scaffold** only, not full SENTINEL
- MongoDB disabled in `application.properties` for early steps (but Spring Data still connects if MongoDB is running)
- **Structure:** `d:\Tutorials\mercenary\` contains `mercenary-tutorial` (code) and `mercenary-tutorial-documentation` (docs)

## Next Action
Step 5: Add dependencies per STEP-05.md. Goal: full clone (~55 steps) for customer-facing understanding. See ROADMAP.md, CUSTOMER-VALUE.md.
