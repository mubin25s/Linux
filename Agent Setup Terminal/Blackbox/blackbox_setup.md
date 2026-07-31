# ⬛ Blackbox AI — Setup Guide (Terminal & VS Code)

Blackbox AI is an AI coding assistant that integrates into your terminal and code editor. It offers autocomplete, chat, and terminal command suggestions.

---

## ✅ Prerequisites

| Requirement | Version | Check Command |
| :--- | :--- | :--- |
| Node.js | ≥ 16.0 | `node --version` |
| npm | ≥ 7.0 | `npm --version` |
| VS Code | Any (for extension) | `code --version` |
| Blackbox Account | Free | [blackbox.ai](https://blackbox.ai) |

---

## 🪟 Step 1 — Install Node.js (if not installed)

### Windows
```powershell
winget install OpenJS.NodeJS
node --version
```

### Linux (Ubuntu/Debian)
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
node --version
```

### macOS
```bash
brew install node
node --version
```

---

## 📦 Step 2 — Install Blackbox CLI

```bash
# Install globally via npm
npm install -g @blackboxapp/blackbox

# Verify
blackbox --version
```

---

## 🔑 Step 3 — Create a Free Account

1. Go to [blackbox.ai](https://www.blackbox.ai)
2. Click **Sign Up** (free account available)
3. Confirm your email

---

## ⚙️ Step 4 — Login via CLI

```bash
# Login with your Blackbox account
blackbox login

# Follow the browser prompt or enter credentials
```

---

## 🚀 Step 5 — Run Blackbox in Terminal

```bash
# Start interactive Blackbox chat
blackbox chat

# Ask a coding question
blackbox ask "How do I reverse a string in Python?"

# Get terminal command suggestions
blackbox cmd "find all .log files older than 7 days"

# Search for code snippets
blackbox search "React useEffect cleanup"
```

---

## 💡 Common CLI Commands

| Command | Description |
| :--- | :--- |
| `blackbox chat` | Start interactive AI chat |
| `blackbox ask "question"` | One-shot code question |
| `blackbox cmd "task"` | Get terminal command suggestion |
| `blackbox search "topic"` | Search code snippets |
| `blackbox login` | Authenticate |
| `blackbox logout` | Log out |
| `blackbox --help` | Show all commands |
| `blackbox --version` | Show version |

---

## 🖥️ VS Code Extension Setup

### Install via VS Code Marketplace

1. Open VS Code
2. Press `Ctrl+Shift+X` (Extensions panel)
3. Search: **Blackbox AI**
4. Click **Install**

### Install via Command Line
```bash
code --install-extension Blackboxapp.blackbox
```

### Activate the Extension
1. After install, open any code file
2. Press `Ctrl+Shift+P` → type `Blackbox: Login`
3. Sign in with your account

---

## ⌨️ VS Code Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `Tab` | Accept autocomplete suggestion |
| `Ctrl+Shift+A` | Open Blackbox AI chat |
| `Ctrl+Shift+B` | Explain selected code |
| `Alt+\` | Trigger inline suggestion manually |

---

## 🔄 Update Blackbox CLI

```bash
npm update -g @blackboxapp/blackbox
```

---

## 🗑️ Uninstall

```bash
# Uninstall CLI
npm uninstall -g @blackboxapp/blackbox

# Uninstall VS Code extension
code --uninstall-extension Blackboxapp.blackbox
```

---

## ❗ Troubleshooting

| Problem | Fix |
| :--- | :--- |
| `blackbox: command not found` | Re-run the npm install command |
| Login fails | Try `blackbox logout` then `blackbox login` again |
| Autocomplete not working (VS Code) | Disable conflicting extensions (Copilot, Tabnine) |
| Extension not showing | Reload VS Code with `Ctrl+Shift+P` → *Reload Window* |

---

> 📌 **Official Site**: [blackbox.ai](https://www.blackbox.ai)
> 📌 **VS Code Extension**: [marketplace.visualstudio.com/items?itemName=Blackboxapp.blackbox](https://marketplace.visualstudio.com/items?itemName=Blackboxapp.blackbox)
