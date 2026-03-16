# Step 7: Enable MongoDB, Configure Connection

## Objective
Enable MongoDB and configure the connection. The app will connect to a local MongoDB instance (or a URI you provide).

## Prerequisites
- Step 6 complete (application.yaml in place)
- MongoDB running locally, or a MongoDB Atlas URI

## MongoDB Options

| Option | Use case |
|--------|----------|
| **Local** | Run MongoDB on your machine (Docker or native install) |
| **Atlas** | Free tier at [mongodb.com/atlas](https://www.mongodb.com/atlas) — cloud-hosted |

**Don't have MongoDB yet?** You can still do this step. The app will fail to start until MongoDB is available, but the config will be correct. Or use MongoDB Atlas free tier and paste the connection string.

## Instructions

### 1. Edit application.yaml

Open `src/main/resources/application.yaml` and make these changes:

**Remove** the `autoconfigure.exclude` block (the MongoDB exclusion):

```yaml
  autoconfigure:
    exclude:
      - org.springframework.boot.autoconfigure.mongo.MongoAutoConfiguration
```

**Add** the MongoDB URI under `spring.data.mongodb`. Your `spring:` section should look like this:

```yaml
spring:
  application:
    name: mercenary
  data:
    mongodb:
      uri: ${MONGODB_URI:mongodb://localhost:27017/mercenary}

server:
  port: 8081
```

**Copy-paste tip:** Copy only the YAML—not the `yaml` label.

### 2. What This Does

| Part | Meaning |
|-----|---------|
| `${MONGODB_URI:...}` | Use env var `MONGODB_URI` if set; otherwise use the default |
| `mongodb://localhost:27017/mercenary` | Local MongoDB, database name `mercenary` |

**For MongoDB Atlas:** Set `MONGODB_URI` in your environment or run config, e.g.  
`MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/mercenary`

**For local MongoDB with authentication:** Use the full URI including credentials:  
`MONGODB_URI=mongodb://username:password@localhost:27017/mercenary`

### 3. Start MongoDB (if running locally)

MongoDB must be running before the app starts. Choose one:

| Method | Command / Action |
|--------|------------------|
| **Docker** | `docker run -d -p 27017:27017 --name mongo mongo` |
| **Windows service** | Start MongoDB from Services (`services.msc`) |
| **macOS (Homebrew)** | `brew services start mongodb-community` |
| **Atlas** | Skip — MongoDB runs in the cloud |

### 4. Verify

1. **If MongoDB is running locally:**
   - From `d:\Tutorials\mercenary\mercenary-tutorial`: `.\gradlew bootRun`
   - Open http://localhost:8081 — app should start

2. **If using Atlas:** Set `MONGODB_URI` then run the app

3. **If MongoDB isn't ready:** The config is correct; the app will fail with a connection error until MongoDB is available

## Verification

- [ ] `autoconfigure.exclude` for MongoAutoConfiguration is removed
- [ ] `spring.data.mongodb.uri` is present
- [ ] App starts when MongoDB is available (or you see a clear connection error)

## Troubleshooting

**"Connection refused"** — MongoDB isn't running. Start it (e.g. `docker run -p 27017:27017 mongo`) or use Atlas.

**"Authentication failed"** — Check username/password in the URI. For Atlas, ensure the user has read/write access to the database.

**Want to skip MongoDB for now?** Re-add the `autoconfigure.exclude` block and the app will run without MongoDB again.

## Ready to Continue?

Reply with **"Step 7 complete"** and I'll provide Step 8 (Add SecurityConfig — dev mode, permit / and /api).
