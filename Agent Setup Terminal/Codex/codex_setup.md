# 🟢 OpenAI Codex CLI — AI Agent Setup Guide

OpenAI Codex CLI is a lightweight, open-source coding agent that runs in your terminal. It can read your codebase, write code, run commands, and iterate — all from the command line.

---

## ✅ Prerequisites

| Requirement | Version | Check Command |
| :--- | :--- | :--- |
| Node.js | ≥ 22.0 | `node --version` |
| npm | ≥ 8.0 | `npm --version` |
| Git | Any | `git --version` |
| OpenAI API Key | — | [platform.openai.com](https://platform.openai.com) |

---

## 🪟 Step 1 — Install Node.js ≥ 22 (Required)

### Windows
```powershell
winget install OpenJS.NodeJS.LTS

# Verify (must be ≥ 22)
node --version
```

### Linux (Ubuntu/Debian)
```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

node --version
```

### macOS
```bash
brew install node@22
node --version
```

---

## 📦 Step 2 — Install Codex CLI

```bash
# Install globally via npm
npm install -g @openai/codex

# Verify installation
codex --version
```

---

## 🔑 Step 3 — Get Your OpenAI API Key

1. Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
2. Sign in or create an account
3. Click **Create new secret key**
4. Copy your key (starts with `sk-...`)

> ⚠️ **Note**: Codex CLI requires a paid OpenAI account with available credits.

---

## ⚙️ Step 4 — Configure API Key

### Windows (PowerShell — current session)
```powershell
$env:OPENAI_API_KEY = "sk-your-key-here"
```

### Windows (permanent)
```powershell
[System.Environment]::SetEnvironmentVariable("OPENAI_API_KEY", "sk-your-key-here", "User")
# Restart terminal after this
```

### Linux / macOS (permanent)
```bash
echo 'export OPENAI_API_KEY="sk-your-key-here"' >> ~/.bashrc
source ~/.bashrc

# Zsh users
echo 'export OPENAI_API_KEY="sk-your-key-here"' >> ~/.zshrc
source ~/.zshrc
```

---

## 🚀 Step 5 — Run Codex CLI

```bash
# Start interactive session in your project
codex

# One-shot task
codex "Fix the bug in main.py"

# Full auto mode (runs without asking for approval)
codex --approval-mode full-auto "Refactor this function"

# Specify a model
codex --model o4-mini "Add unit tests"

# Quiet mode (non-interactive)
codex --quiet "List all TODOs in this codebase"
```

---

## 💡 Common Commands & Flags

| Command / Flag | Description |
| :--- | :--- |
| `codex` | Start interactive agent session |
| `codex "task"` | Run a one-shot coding task |
| `codex --help` | Show all available options |
| `codex --version` | Show installed version |
| `codex --model <model>` | Select OpenAI model |
| `codex --approval-mode suggest` | Suggest changes only (safe, default) |
| `codex --approval-mode auto-edit` | Auto-edit files, ask before running |
| `codex --approval-mode full-auto` | Fully autonomous — no prompts |
| `codex --quiet` | Suppress verbose output |

---

## 🧠 Approval Modes Explained

| Mode | File Edits | Shell Commands | Best For |
| :--- | :--- | :--- | :--- |
| `suggest` | Manual | Manual | Learning, reviewing |
| `auto-edit` | Auto | Manual | Daily coding |
| `full-auto` | Auto | Auto | Trusted, sandboxed use |

---

## 🧠 Available Models

| Model | Use Case |
| :--- | :--- |
| `o4-mini` | Fast, cost-effective coding (recommended) |
| `o3` | Advanced reasoning tasks |
| `gpt-4.1` | General purpose |

---

## 🔄 Update Codex CLI

```bash
npm update -g @openai/codex

# Check installed version
npm list -g @openai/codex
```

---

## 🗑️ Uninstall

```bash
npm uninstall -g @openai/codex
```

---

## ❗ Troubleshooting

| Problem | Fix |
| :--- | :--- |
| `codex: command not found` | Re-run `npm install -g @openai/codex` |
| API key error | Verify `OPENAI_API_KEY` is set correctly |
| Node version error | Upgrade Node.js to ≥ 22 |
| Insufficient quota | Add credits at platform.openai.com |
| Permission error (Linux/Mac) | Use `sudo` or fix npm global permissions |

---

## 🔐 Fix npm Global Permission (Linux/macOS)

```bash
mkdir -p ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
```

---

> 📌 **Official Repo**: [github.com/openai/codex](https://github.com/openai/codex)
