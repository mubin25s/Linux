# 💎 Gemini CLI — AI Agent Setup Guide

Google Gemini CLI is an open-source terminal agent that brings the power of Google's Gemini models directly into your shell. It can read files, run commands, and act as a coding agent.

---

## ✅ Prerequisites

| Requirement | Version | Check Command |
| :--- | :--- | :--- |
| Node.js | ≥ 18.0 | `node --version` |
| npm | ≥ 8.0 | `npm --version` |
| Git | Any | `git --version` |
| Google Account | — | [aistudio.google.com](https://aistudio.google.com) |

---

## 🪟 Step 1 — Install Node.js (if not installed)

### Windows
```powershell
winget install OpenJS.NodeJS

# Verify
node --version
npm --version
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

## 📦 Step 2 — Install Gemini CLI

```bash
# Install globally via npm
npm install -g @google/gemini-cli

# Verify installation
gemini --version
```

---

## 🔑 Step 3 — Get Your API Key

1. Go to [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
2. Sign in with your Google account
3. Click **Create API Key**
4. Copy your key (starts with `AIza...`)

---

## ⚙️ Step 4 — Configure API Key

### Windows (PowerShell — current session)
```powershell
$env:GEMINI_API_KEY = "AIza-your-key-here"
```

### Windows (permanent)
```powershell
[System.Environment]::SetEnvironmentVariable("GEMINI_API_KEY", "AIza-your-key-here", "User")
```

### Linux / macOS (permanent)
```bash
echo 'export GEMINI_API_KEY="AIza-your-key-here"' >> ~/.bashrc
source ~/.bashrc

# Zsh users
echo 'export GEMINI_API_KEY="AIza-your-key-here"' >> ~/.zshrc
source ~/.zshrc
```

### Option B: Login with Google OAuth (No API Key needed)
```bash
# Run Gemini — it will open a browser for Google login on first run
gemini
```
> ✅ **Tip**: Google login gives you **free usage** (Gemini 2.5 Pro) with a personal Google account — no API key required!

---

## 🚀 Step 5 — Run Gemini CLI

```bash
# Start interactive Gemini agent session
gemini

# One-shot query
gemini "What does this project do?"

# Specify a model
gemini --model gemini-2.5-pro

# Use in a specific directory
cd /your/project && gemini
```

---

## 💡 Common Commands

| Command | Description |
| :--- | :--- |
| `gemini` | Start interactive session |
| `gemini "question"` | One-shot query |
| `gemini --help` | Show all flags |
| `gemini --version` | Show installed version |
| `gemini --model <model>` | Select Gemini model |
| `gemini --yolo` | Auto-approve all actions (use carefully!) |

---

## 🧠 Available Models

| Model | Use Case |
| :--- | :--- |
| `gemini-2.5-pro` | Best reasoning & coding (default) |
| `gemini-2.5-flash` | Faster, lighter tasks |
| `gemini-1.5-pro` | Stable, long-context tasks |

---

## 🔄 Update Gemini CLI

```bash
npm update -g @google/gemini-cli

# Check current version
npm list -g @google/gemini-cli
```

---

## 🗑️ Uninstall

```bash
npm uninstall -g @google/gemini-cli
```

---

## ❗ Troubleshooting

| Problem | Fix |
| :--- | :--- |
| `gemini: command not found` | Re-run `npm install -g @google/gemini-cli` |
| API key error | Verify `GEMINI_API_KEY` env variable is set |
| Auth browser won't open | Run `gemini` in a non-headless terminal |
| Permission denied (Linux/Mac) | Fix npm permissions or use `sudo` |

---

> 📌 **Official Docs**: [github.com/google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli)
