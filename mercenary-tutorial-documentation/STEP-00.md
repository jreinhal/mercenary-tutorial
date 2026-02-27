# Step 0: Generate the Project with Spring Initializr

## Objective
Create the project from scratch using Spring Initializr. **Use this step only if you don't have the scaffold yet.** If you already have `d:\Tutorials\mercenary\mercenary-tutorial`, skip to Step 1.

## Prerequisites
- **Java 21** installed
- **Web browser**
- **Cursor IDE** (or any editor)

## Fundamentals

**Spring Initializr** (start.spring.io) generates a Spring Boot project with the correct structure, build file, and starter dependencies. It's the standard way to bootstrap a Spring Boot project.

## Instructions

### 1. Open Spring Initializr

Go to **https://start.spring.io** in your browser.

### 2. Configure Project Settings

| Field | Value |
|-------|-------|
| **Project** | Gradle - Groovy |
| **Language** | Java |
| **Spring Boot** | 3.4.x (select 3.4—needed for Spring AI in Step 5) |
| **Group** | `com.jreinhal` |
| **Artifact** | `mercenary` |
| **Name** | mercenary (auto-filled) |
| **Packaging** | Jar |
| **Java** | 21 |

### 3. Add Dependencies

Click **"ADD DEPENDENCIES"** and add:

- **Spring Web** – REST APIs and web support
- **Spring Data MongoDB** – MongoDB integration (for vector store)
- **Spring Boot DevTools** – Hot reload during development

### 4. Generate and Download

Click the green **GENERATE** button. A ZIP file will download.

### 5. Extract the Project

1. Create folder `d:\Tutorials\mercenary` if it doesn't exist
2. Extract the ZIP into `d:\Tutorials\mercenary\` — you'll get `d:\Tutorials\mercenary\mercenary` (Spring Initializr uses the artifact name)
3. Rename the inner `mercenary` folder to `mercenary-tutorial` (final path: `d:\Tutorials\mercenary\mercenary-tutorial`)

### 6. Add Development Config (so the app can run without MongoDB)

Open `src/main/resources/application.properties` and add these lines **after** the existing content:

```properties
# Tutorial uses 8081 to avoid conflict with other apps on 8080
server.port=8081

# Temporarily disable MongoDB—we'll enable it in a later step
spring.autoconfigure.exclude=org.springframework.boot.autoconfigure.mongo.MongoAutoConfiguration
```

This lets the app start without MongoDB. We'll enable MongoDB in Step 7.

### 7. Open in Cursor

1. In Cursor: **File → Open Folder** (or `Ctrl+K Ctrl+O`)
2. Navigate to `d:\Tutorials\mercenary\mercenary-tutorial`
3. Click **Select Folder**

## What You'll Have

```
mercenary-tutorial/
├── build.gradle
├── gradlew / gradlew.bat
├── settings.gradle
├── src/
│   ├── main/
│   │   ├── java/com/jreinhal/mercenary/
│   │   │   └── MercenaryApplication.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/com/jreinhal/mercenary/
│           └── MercenaryApplicationTests.java
└── ...
```

## Verification

- [ ] Project extracted to `d:\Tutorials\mercenary\mercenary-tutorial`
- [ ] `MercenaryApplication.java` exists with `@SpringBootApplication`
- [ ] `build.gradle` lists Spring Web, Spring Data MongoDB, DevTools
- [ ] Project opens in Cursor without errors

## Ready to Continue?

Reply with **"Step 0 complete"** and proceed to **Step 1** (Open the project and verify structure). If you already had the scaffold, Step 1 will be quick.
