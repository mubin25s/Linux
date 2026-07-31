# 🤖 Claude (Anthropic) — AI Agent Setup Guide

Claude is Anthropic's AI assistant. The official CLI is **Claude Code**, which lets you run Claude directly in your terminal as a coding agent.

---

## ✅ Prerequisites

| Requirement | Version | Check Command |
| :--- | :--- | :--- |
| Node.js | ≥ 18.0 | `node --version` |
| npm | ≥ 8.0 | `npm --version` |
| Git | Any | `git --version` |
| Anthropic API Key | — | [console.anthropic.com](https://console.anthropic.com) |

---

## 🪟 Step 1 — Install Node.js (if not installed)

### Windows
```powershell
# Using winget
winget install OpenJS.NodeJS

# OR using Chocolatey
choco install nodejs

# Verify
node --version
npm --version
```

### Linux (Ubuntu/Debian)
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs

# Verify
node --version
npm --version
```

### macOS
```bash
brew install node

# Verify
node --version
npm --version
```

---

## 📦 Step 2 — Install Claude Code CLI

```bash
# Install globally via npm
npm install -g @anthropic-ai/claude-code

# Verify installation
claude --version
```

---

## 🔑 Step 3 — Get Your API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up or log in
3. Navigate to **API Keys** → Click **Create Key**
4. Copy your key (starts with `sk-ant-...`)

---

## ⚙️ Step 4 — Configure API Key

### Option A: Set as Environment Variable (Recommended)

**Windows (PowerShell — temporary, current session)**
```powershell
$env:ANTHROPIC_API_KEY = "sk-ant-your-key-here"
```

**Windows (permanent — system environment)**
```powershell
[System.Environment]::SetEnvironmentVariable("ANTHROPIC_API_KEY", "sk-ant-your-key-here", "User")
```

**Linux / macOS (temporary)**
```bash
export ANTHROPIC_API_KEY="sk-ant-your-key-here"
```

**Linux / macOS (permanent — add to shell profile)**
```bash
echo 'export ANTHROPIC_API_KEY="sk-ant-your-key-here"' >> ~/.bashrc
source ~/.bashrc

# For Zsh users
echo 'export ANTHROPIC_API_KEY="sk-ant-your-key-here"' >> ~/.zshrc
source ~/.zshrc
```

### Option B: Login via CLI
```bash
claude login
# Follow the browser prompt to authenticate
```

---

## 🚀 Step 5 — Run Claude Code

```bash
# Start Claude in your current project directory
claude

# Ask a one-shot question
claude "Explain what this code does"

# Start in a specific folder
claude --project /path/to/your/project

# Run with a specific model
claude --model claude-opus-4-5
```

---

## 💡 Common Commands

| Command | Description |
| :--- | :--- |
| `claude` | Start interactive Claude session |
| `claude "your question"` | One-shot query |
| `claude --help` | Show all available flags |
| `claude --version` | Show installed version |
| `claude --model <model>` | Specify which Claude model to use |
| `claude login` | Authenticate via browser |
| `claude logout` | Remove stored credentials |

---

## 🔄 Update Claude Code

```bash
npm update -g @anthropic-ai/claude-code

# Check for latest version
npm outdated -g @anthropic-ai/claude-code
```

---

## 🗑️ Uninstall

```bash
npm uninstall -g @anthropic-ai/claude-code
```

---

## ❗ Troubleshooting

| Problem | Fix |
| :--- | :--- |
| `claude: command not found` | Run `npm install -g @anthropic-ai/claude-code` again |
| API key not recognized | Double-check env variable is set correctly |
| Permission denied (Linux/Mac) | Use `sudo npm install -g` or fix npm permissions |
| `node` not found | Install Node.js ≥ 18 first |

---

> 📌 **Official Docs**: [docs.anthropic.com/claude-code](https://docs.anthropic.com/en/docs/claude-code)
