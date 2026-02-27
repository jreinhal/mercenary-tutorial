# Step 2: Run the Application

## Objective
Run the tutorial project locally. The tutorial scaffold runs without MongoDB or Ollama—we'll add those in later steps.

---

## Tutorial Path: Run the Scaffold (d:\Tutorials\mercenary\mercenary-tutorial)

**Use this path** if you're following the tutorial and building from the scaffold. MongoDB is disabled in config—no external services needed.

### Prerequisites
- **Java 21** installed (`java -version`)

### Steps

1. **Open the terminal** – Press `Ctrl+` ` (backtick)
2. **Navigate to project** – `cd d:\Tutorials\mercenary\mercenary-tutorial` (if needed)
3. **Run the application:**
   ```powershell
   .\gradlew bootRun
   ```
4. **Wait for startup** – Look for `Started MercenaryApplication in X.XXX seconds`
5. **Verify** – The app starts on port 8081. There's no UI yet (we add that later). Press `Ctrl+C` to stop.

**Note:** Tutorial uses port 8081. MongoDB is disabled in `application.properties`. We'll enable and configure it in a later step.

---

## Full SENTINEL Path: Run Production App (D:\Projects\mercenary)

**Use this path** if you want to run the complete SENTINEL platform with RAG, chat, and ingestion.

### Prerequisites
- **Java 21** installed
- **MongoDB** running on `localhost:27017`
- **Ollama** running on `localhost:11434`
- Models: `ollama pull llama3.1:8b` and `ollama pull bge-m3`

### Steps

1. **Open the terminal** – Press `Ctrl+` ` (backtick)
2. **Navigate** – `cd D:\Projects\mercenary`
3. **Set environment variables:**
   ```powershell
   $env:APP_PROFILE="dev"
   $env:MONGODB_URI="mongodb://localhost:27017/mercenary"
   $env:OLLAMA_URL="http://localhost:11434"
   $env:LLM_MODEL="llama3.1:8b"
   $env:EMBEDDING_MODEL="bge-m3"
   ```
4. **Run** – `.\gradlew bootRun`
5. **Open browser** – http://localhost:8081 for the SENTINEL dashboard (tutorial scaffold uses 8081)
6. **Stop** – `Ctrl+C` in the terminal

---

## Instructions (Tutorial Path)

### 1. Open the Terminal

1. Press `Ctrl+` ` (backtick) to open the integrated terminal
2. Confirm the prompt shows the project root (e.g., `PS D:\Tutorials\mercenary\mercenary-tutorial>`)
3. If not, run: `cd d:\Tutorials\mercenary\mercenary-tutorial`

### 2. Run the Application

```powershell
.\gradlew bootRun
```

No environment variables needed for the tutorial scaffold.

### 3. Wait for Startup

- First run may take 1–2 minutes (Gradle downloads dependencies)
- Look for: `Started MercenaryApplication in X.XXX seconds`

### 4. Stop the Application

Press `Ctrl+C` in the terminal to stop the server.

**Note:** The scaffold has no web UI yet—we're just verifying the Spring Boot app starts. We'll add controllers and features in later steps.

## Step-by-Step: Tutorial Run Sequence

1. **Open terminal in Cursor** – `Ctrl+` `.

2. **Navigate to project** – `cd d:\Tutorials\mercenary\mercenary-tutorial` (if needed).

3. **Run** – `.\gradlew bootRun` and press Enter.

4. **Wait** – Watch for "Started MercenaryApplication". Ignore initial Gradle output.

5. **Stop** – `Ctrl+C` in the terminal.

## Verification (Tutorial Path)

| Check | Expected |
|-------|----------|
| Build | "BUILD SUCCESSFUL" or app starts without build errors |
| Startup | "Started MercenaryApplication" in logs |
| MongoDB | Not required—disabled in application.properties |

## Troubleshooting

### App hangs at 80% or during startup (Tutorial path)
- The tutorial scaffold has MongoDB disabled—it should not hang. If it does, check for errors in the terminal.
- Try `.\gradlew bootRun --info` for more logging.

### Port 8081 already in use
- Stop the other process using 8081, or
- Set `server.port=8082` in application.properties

### "Connection refused" to MongoDB (Full SENTINEL path only)
- Ensure MongoDB is running: `mongosh` or check port 27017
- Verify `MONGODB_URI` is correct

### "Connection refused" to Ollama (Full SENTINEL path only)
- Ensure Ollama is running: `ollama list` should work
- Verify `OLLAMA_URL` is `http://localhost:11434`

## Ready to Continue?

Once the application runs and you can access the UI, reply with **"Step 2 complete"** and I'll provide Step 3 (Explore the Architecture).
