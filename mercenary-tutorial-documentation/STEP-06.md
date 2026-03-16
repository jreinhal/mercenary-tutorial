# Step 6: Create application.yaml

## Objective
Migrate from `application.properties` to `application.yaml`. YAML is easier to read for nested config and is what SENTINEL uses.

## Prerequisites
- Step 5 complete
- Tutorial scaffold open in Cursor

## Why YAML?

| Format | Pros |
|--------|------|
| **properties** | Simple, flat key=value |
| **yaml** | Hierarchical, less repetition, comments, standard for Spring Boot config |

Spring Boot loads both. If both exist, `.yaml` takes precedence over `.properties` for overlapping keys.

## Instructions

### 1. Create application.yaml

**You create this file.** In Cursor:

1. Right-click `src/main/resources/` in the file explorer
2. Select **New File**
3. Type `application.yaml`

### 2. Add the Configuration

Paste the following into `application.yaml`:

```yaml
spring:
  application:
    name: mercenary
  autoconfigure:
    exclude:
      - org.springframework.boot.autoconfigure.mongo.MongoAutoConfiguration

server:
  port: 8081
```

**Copy-paste tip:** Copy only the lines inside the code block—not the `yaml` label.

### 3. Remove or Rename application.properties

**Option A (recommended):** Delete `application.properties`. All config is now in `application.yaml`.

**Option B:** Rename it to `application.properties.bak` if you want to keep a backup.

### 4. Verify

1. Save all files
2. From `d:\Tutorials\mercenary\mercenary-tutorial`: `.\gradlew bootRun`
3. Open http://localhost:8081 — you should see the welcome message (or a login page—see note below)
4. Stop the app (`Ctrl+C`)

**Login page?** Spring Security (added in Step 5) may show a login page instead of the welcome message. That's expected. Log in with the username and password printed in the console, or wait for Step 8 to permit public access.

## YAML Structure Quick Reference

```yaml
# Nested keys use indentation (spaces, not tabs)
spring:
  application:
    name: mercenary    # spring.application.name
  autoconfigure:
    exclude:           # spring.autoconfigure.exclude (list)
      - some.Class
```

## Verification

- [ ] `src/main/resources/application.yaml` exists
- [ ] `application.properties` is removed or renamed
- [ ] `.\gradlew bootRun` starts the app
- [ ] http://localhost:8081 shows the welcome message or a login page (both are expected)

## Troubleshooting

**App won't start** — Check YAML indentation. Use spaces, not tabs. Each level is typically 2 spaces.

**Port already in use** — Another process is using 8081. Stop it or change `server.port` in the YAML.

**Login page instead of welcome message** — Expected after Step 5. Spring Security requires auth. Step 8 will add a dev config to permit `/` and `/api`.

## Ready to Continue?

Reply with **"Step 6 complete"** and I'll provide Step 7 (Enable MongoDB, configure connection).
