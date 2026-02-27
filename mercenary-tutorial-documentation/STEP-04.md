# Step 4: Make a Small Change

## Objective
Add a simple REST controller so `http://localhost:8081/` returns a welcome message instead of the Whitelabel error page.

## Prerequisites
- Steps 1–3 complete
- Tutorial scaffold open in Cursor

## Instructions

### 1. Create the Controller

**You create this file.** In Cursor:

1. Right-click `src/main/java/com/jreinhal/mercenary/` in the file explorer
2. Select **New File**
3. Type `controller/HomeController.java` (this creates the `controller` folder and file)
4. Paste or type the following:

**Contents:**
```java
package com.jreinhal.mercenary.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HomeController {

    @GetMapping("/")
    public String home() {
        return "Welcome to SENTINEL Tutorial. The app is running.";
    }
}
```

### 2. Run the Application

1. Open terminal (`Ctrl+` `)
2. From `d:\Tutorials\mercenary\mercenary-tutorial`: `.\gradlew bootRun`
3. Wait for "Started MercenaryApplication"

### 3. Verify

1. Open http://localhost:8081 in a browser
2. You should see: **"Welcome to SENTINEL Tutorial. The app is running."**
3. Press `Ctrl+C` to stop

## What You Added

- **`@RestController`** – Marks the class as a REST controller; Spring maps HTTP requests to its methods
- **`@GetMapping("/")`** – Maps GET requests to the root path `/` to the `home()` method
- **Return value** – Sent as the response body (plain text by default)

## Verification Checklist

- [ ] HomeController.java exists in `controller` package
- [ ] App starts without errors
- [ ] http://localhost:8081 shows the welcome message

## Ready to Continue?

You've completed the tutorial scaffold basics. Reply with **"Step 4 complete"** or ask for the next step (e.g., add more endpoints, enable MongoDB, etc.).
