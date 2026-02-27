# Step 5: Add Dependencies

## Objective
Add Lombok, Spring Security, and Spring AI (Ollama) to `build.gradle`. These are the core dependencies we need to build the SENTINEL clone.

## Prerequisites
- Steps 1–4 complete
- Tutorial scaffold open in Cursor

## Fundamentals

| Dependency | Purpose |
|------------|---------|
| **Lombok** | Reduces boilerplate (getters, setters, etc.) in model classes |
| **Spring Security** | Authentication and authorization; we'll configure it in a later step |
| **Spring AI Ollama** | Connects to local Ollama for LLM chat and embeddings |

## Instructions

**You edit `build.gradle`.** Open `d:\Tutorials\mercenary\mercenary-tutorial\build.gradle` and make these changes:

### 1. Update Spring Boot Version

Change the Spring Boot version to 3.4.13 (for Spring AI compatibility):

```groovy
id 'org.springframework.boot' version '3.4.13'
```

### 2. Add Spring Milestone Repository

Inside `repositories { }`, add this line **after** `mavenCentral()`:

```groovy
maven { url 'https://repo.spring.io/milestone' }
```

### 3. Add Dependencies

Inside `dependencies { }`, add these lines **after** the existing `implementation` lines (before `developmentOnly`):

```groovy
	compileOnly 'org.projectlombok:lombok'
	annotationProcessor 'org.projectlombok:lombok'
	implementation 'org.springframework.boot:spring-boot-starter-security'
	implementation 'org.springframework.ai:spring-ai-ollama-spring-boot-starter:1.0.0-M4'
```

### 4. Add Spring AI BOM

Add this block **after** the `repositories { }` block and **before** `dependencies { }`:

```groovy
dependencyManagement {
	imports {
		mavenBom 'org.springframework.ai:spring-ai-bom:1.0.0-M4'
	}
}
```

### 5. Verify the Build

1. Open terminal (`Ctrl+` `)
2. From `d:\Tutorials\mercenary\mercenary-tutorial`: `.\gradlew build`
3. Wait for "BUILD SUCCESSFUL"

**Note:** Spring Security will add a default login. When you run the app, you may see a login page at `/` until we configure Security in Step 8. We'll fix that in a later step.

**Scaffold note:** If your scaffold has Spring Boot 4.0.2, Step 5 changes it to 3.4.13 for Spring AI compatibility. If you have `spring-boot-starter-webmvc`, keep it—it's equivalent to `spring-boot-starter-web` for our purposes.

## Step-by-Step: Edit build.gradle

1. Open `build.gradle` in the editor
2. Make each change above
3. Save (`Ctrl+S`)
4. Run `.\gradlew build` in the terminal
5. Confirm "BUILD SUCCESSFUL"

## Verification

- [ ] Spring Boot version is 3.4.13
- [ ] `maven { url 'https://repo.spring.io/milestone' }` is in repositories
- [ ] Lombok, Security, Spring AI Ollama are in dependencies
- [ ] `dependencyManagement` block with Spring AI BOM is present
- [ ] `.\gradlew build` succeeds

## Troubleshooting

**Build fails with "Could not resolve"** — Check the dependency names and the milestone repository. Ensure no typos.

**Spring AI version not found** — The milestone repo must be present. Run `.\gradlew build --refresh-dependencies`.

## Ready to Continue?

Reply with **"Step 5 complete"** and I'll provide Step 6 (Create application.yaml).
