# Cursor IDE Quick Reference Guide

Welcome to Cursor! This guide helps you navigate and use Cursor effectively when working with SENTINEL.

**SENTINEL project path:** `D:\Projects\mercenary`  
**Tutorial documentation:** `D:\Tutorials\mercenary\mercenary-tutorial-documentation`

**Quick commands (from project root):**
- Run: `.\gradlew bootRun`
- Build: `.\gradlew build`
- Test: `.\gradlew test`

## What is Cursor?

Cursor is an AI-powered code editor based on VS Code. It includes:
- **AI Chat** (that's me!) - Get help, ask questions, generate code
- **Composer** - AI-powered code generation and editing
- **Code Actions** - AI suggestions for your code
- **All VS Code features** - Extensions, debugging, Git integration, etc.

## Essential Keyboard Shortcuts

### Navigation
- `Ctrl+Shift+E` - Toggle file explorer
- `Ctrl+P` - Quick file open (type filename to search)
- `Ctrl+Shift+F` - Search across all files
- `Ctrl+` ` (backtick) - Toggle terminal
- `Ctrl+B` - Toggle sidebar

### AI Features
- `Ctrl+L` - Open AI Chat (this is how you talk to me!)
- `Ctrl+I` - Open Composer (inline AI assistance)
- `Ctrl+K` - Quick AI edit (select code, press Ctrl+K, describe change)
- `Ctrl+Shift+L` - AI code actions menu

### Editing
- `Ctrl+N` - New file
- `Ctrl+S` - Save file
- `Ctrl+Z` - Undo
- `Ctrl+Shift+P` - Command palette (do anything!)

## Working with Files

### Creating Files/Folders
1. **Right-click** in file explorer → "New File" or "New Folder"
2. Or use `Ctrl+N` to create a new file
3. Or use terminal: `New-Item -ItemType File -Path "filename.txt"`

### Opening Files
- Click file in explorer
- Use `Ctrl+P` and type filename
- Use `Ctrl+O` to browse

### Saving Files
- `Ctrl+S` - Save current file
- `Ctrl+K S` - Save all files
- Files auto-save is usually enabled by default

## Using the Terminal

Cursor includes an integrated terminal (PowerShell on Windows).

### Opening Terminal
- `Ctrl+` ` (backtick)
- View → Terminal
- `Ctrl+Shift+P` → "Terminal: Create New Terminal"

### Common Commands (PowerShell)
```powershell
# List files
Get-ChildItem
# or
ls
dir

# Change directory
cd path\to\folder

# Create directory
New-Item -ItemType Directory -Path "foldername"
# or
mkdir foldername

# Create file
New-Item -ItemType File -Path "filename.txt"

# Run Gradle commands
.\gradlew build
.\gradlew bootRun
```

## Using AI Chat (Me!)

### Opening Chat
- Press `Ctrl+L`
- Or click the chat icon in the sidebar
- Or use command palette: `Ctrl+Shift+P` → "Chat: New Chat"

### What You Can Ask
- "How do I create a file?"
- "What does this code do?"
- "Help me debug this error"
- "Generate code for..."
- "Explain this concept"

### Best Practices
- Be specific about what you need
- Share error messages or code snippets
- Ask follow-up questions if something isn't clear

## Using Composer (Inline AI)

### When to Use Composer
- Generate code in a specific location
- Refactor existing code
- Add features to existing files

### How to Use
1. Press `Ctrl+I`
2. Describe what you want
3. Review the generated code
4. Accept or modify as needed

## Code Actions

### Quick AI Edits
1. Select code
2. Press `Ctrl+K`
3. Describe the change you want
4. Review and accept

### Right-Click Menu
- Right-click on code
- Select AI-powered actions
- Choose from suggestions

## Debugging

### Setting Breakpoints
- Click left of line numbers (red dot appears)
- Or press `F9` on the line

### Running Debugger
- `F5` - Start debugging
- `Shift+F5` - Stop debugging
- `F10` - Step over
- `F11` - Step into

## Git Integration

### Viewing Changes
- Click the Source Control icon (left sidebar)
- See modified files
- Click file to see diff

### Committing
1. Stage changes (click + icon)
2. Write commit message
3. Click checkmark to commit

## Extensions

### Installing Extensions
- Click Extensions icon (left sidebar)
- Search for extension
- Click Install

### Recommended Extensions
- **Java Extension Pack** - Java development
- **Gradle for Java** - Gradle support
- **Spring Boot Extension Pack** - Spring Boot tools

## Tips for This Tutorial

1. **Keep Chat Open**: Use `Ctrl+L` to keep me available
2. **Use Terminal**: Run Gradle commands in integrated terminal
3. **Ask Questions**: Don't hesitate to ask if something is unclear
4. **Explore**: Try different features as we go
5. **Save Often**: `Ctrl+S` frequently

## Getting Help

- **In Chat**: Ask me anything!
- **Command Palette**: `Ctrl+Shift+P` - type what you want to do
- **VS Code Docs**: Most VS Code features work the same way

## Common Issues

### Terminal Not Working?
- Check if PowerShell is installed
- Try `Ctrl+Shift+P` → "Terminal: Select Default Profile"

### Files Not Showing?
- Refresh explorer: Right-click → "Refresh"
- Check if you're in the right workspace

### AI Not Responding?
- Check internet connection
- Try refreshing chat (`Ctrl+L` then refresh)

---

**Remember**: Cursor is here to help! Don't hesitate to experiment and ask questions. We'll learn together as we build SENTINEL.
