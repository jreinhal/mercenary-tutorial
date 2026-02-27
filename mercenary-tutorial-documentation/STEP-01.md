# Step 1: Open the Project and Verify Structure

## Objective
Open the tutorial project at `d:\Tutorials\mercenary\mercenary-tutorial` in Cursor and verify the codebase structure. This step ensures you have the correct project and can navigate it.

**If you don't have the project yet:** Complete **Step 0** (STEP-00.md) first to generate it with Spring Initializr.

## Project Location

**Path:** `d:\Tutorials\mercenary\mercenary-tutorial`

This is the tutorial scaffold—the project we build step-by-step. If your project is elsewhere, substitute your path.

## Instructions

### 1. Open the Project in Cursor

1. In Cursor: **File → Open Folder** (or `Ctrl+K` then `Ctrl+O`)
2. Navigate to `d:\Tutorials\mercenary\mercenary-tutorial`
3. Click **Select Folder**

### 2. Verify the Root Structure

In the file explorer, you should see:

```
mercenary/
├── build.gradle
├── gradlew / gradlew.bat
├── settings.gradle
├── src/
│   ├── main/
│   │   ├── java/com/jreinhal/mercenary/
│   │   └── resources/
│   └── test/
└── ...
```

### 3. Verify Key Files

| File | What to check |
|------|---------------|
| `build.gradle` | Contains Spring Boot, Spring Web (or WebMVC), Spring Data MongoDB, DevTools |
| `src/main/java/com/jreinhal/mercenary/MercenaryApplication.java` | Has `@SpringBootApplication` and `main()` |
| `src/main/resources/application.properties` | Has `spring.application.name`, MongoDB exclusion |

### 4. Verify Package Structure (Tutorial Scaffold)

Expand `src/main/java/com/jreinhal/mercenary/`. The scaffold starts with:

- `MercenaryApplication.java` – Main application class

We'll add `controller`, `service`, `config`, etc. in later steps.

### 5. Quick Navigation Test

1. Press `Ctrl+P` (Quick Open)
2. Type `MercenaryApplication`
3. Press Enter – you should open the main application class

## Step-by-Step: Open Folder

1. **Open Cursor** – Launch Cursor IDE.

2. **Open the command** – Press `Ctrl+Shift+P` to open the Command Palette.

3. **Type** – "File: Open Folder" and select it.

4. **Navigate** – In the folder picker, go to `d:\Tutorials\mercenary\mercenary-tutorial` (or your project path).

5. **Select** – Click "Select Folder". The project loads in the sidebar.

6. **Confirm** – The file explorer shows the mercenary project. The terminal (when opened) should default to the project root.

## Verification Checklist

- [ ] Project opens without errors
- [ ] `build.gradle` exists and lists Spring Boot, Spring Web, Spring Data MongoDB
- [ ] `MercenaryApplication.java` exists with `@SpringBootApplication`
- [ ] `application.properties` exists
- [ ] `Ctrl+P` → "MercenaryApplication" opens the file

## Troubleshooting

**"Folder not found"** – Confirm the path. The project may be at `d:\Tutorials\mercenary\mercenary-tutorial` or another drive.

**"No Java files"** – Ensure you opened the `mercenary` folder (the one containing `build.gradle`), not a parent folder.

**Java extension not loaded** – Install the "Extension Pack for Java" if prompted. Gradle sync may take a moment.

## Ready to Continue?

Once you've opened the project and verified the structure, reply with **"Step 1 complete"** and I'll provide Step 2 (Run the Application).
