# 📦 OpenCode — AI Agent Setup Guide

OpenCode is an open-source, terminal-based AI coding agent that supports multiple AI providers (OpenAI, Anthropic, Google, Ollama, and more). It runs in your terminal with a beautiful TUI (terminal UI).

---

## ✅ Prerequisites

| Requirement | Version | Check Command |
| :--- | :--- | :--- |
| Go | ≥ 1.21 | `go version` |
| Git | Any | `git --version` |
| API Key | — | Any supported provider |

---

## 🪟 Step 1 — Install Go (if not installed)

### Windows
```powershell
winget install GoLang.Go

# Verify
go version
```

### Linux (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install -y golang-go

# OR install latest manually
wget https://go.dev/dl/go1.22.0.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.22.0.linux-amd64.tar.gz
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
source ~/.bashrc

go version
```

### macOS
```bash
brew install go
go version
```

---

## 📦 Step 2 — Install OpenCode

### Option A: Install via Go (Recommended)
```bash
go install github.com/opencode-ai/opencode@latest

# The binary will be at ~/go/bin/opencode
# Make sure ~/go/bin is in your PATH
```

### Option B: Install via npm (if available)
```bash
npm install -g opencode-ai
opencode --version
```

### Option C: Download prebuilt binary

**Linux / macOS**
```bash
curl -fsSL https://opencode.ai/install.sh | bash
```

**Windows (PowerShell)**
```powershell
irm https://opencode.ai/install.ps1 | iex
```

---

## ⚙️ Step 3 — Add Go binary to PATH

### Windows
```powershell
$env:PATH += ";$env:USERPROFILE\go\bin"

# Permanent
[System.Environment]::SetEnvironmentVariable("PATH", $env:PATH + ";$env:USERPROFILE\go\bin", "User")
```

### Linux / macOS
```bash
echo 'export PATH=$PATH:$HOME/go/bin' >> ~/.bashrc
source ~/.bashrc
```

---

## 🔑 Step 4 — Get an API Key

OpenCode supports multiple providers — pick one:

| Provider | API Key URL |
| :--- | :--- |
| OpenAI | [platform.openai.com/api-keys](https://platform.openai.com/api-keys) |
| Anthropic (Claude) | [console.anthropic.com](https://console.anthropic.com) |
| Google (Gemini) | [aistudio.google.com/apikey](https://aistudio.google.com/apikey) |
| Ollama (local, free) | No key needed — runs locally |

---

## ⚙️ Step 5 — Configure API Key

### Windows (PowerShell)
```powershell
# For OpenAI
$env:OPENAI_API_KEY = "sk-your-key-here"

# For Anthropic
$env:ANTHROPIC_API_KEY = "sk-ant-your-key-here"

# For Gemini
$env:GEMINI_API_KEY = "AIza-your-key-here"
```

### Linux / macOS
```bash
export OPENAI_API_KEY="sk-your-key-here"
export ANTHROPIC_API_KEY="sk-ant-your-key-here"
export GEMINI_API_KEY="AIza-your-key-here"
```

---

## 🚀 Step 6 — Run OpenCode

```bash
# Start OpenCode in current directory
opencode

# Start with a specific provider/model
opencode --model anthropic/claude-opus-4-5
opencode --model openai/gpt-4o
opencode --model google/gemini-2.5-pro

# Start with a specific task
opencode "Fix all TypeScript errors in this project"
```

---

## 💡 Common Commands

| Command | Description |
| :--- | :--- |
| `opencode` | Launch interactive TUI agent |
| `opencode --help` | Show all options |
| `opencode --version` | Show version |
| `opencode --model <provider/model>` | Select AI model |
| `opencode --cwd /path` | Start in a specific directory |

---

## 🧠 Supported Models

| Provider | Model String |
| :--- | :--- |
| OpenAI | `openai/gpt-4o`, `openai/o4-mini` |
| Anthropic | `anthropic/claude-opus-4-5` |
| Google | `google/gemini-2.5-pro` |
| Ollama | `ollama/llama3`, `ollama/codellama` |

---

## 🔄 Update OpenCode

```bash
go install github.com/opencode-ai/opencode@latest
```

---

## 🗑️ Uninstall

```bash
rm $(which opencode)

# Or
rm ~/go/bin/opencode
```

---

## ❗ Troubleshooting

| Problem | Fix |
| :--- | :--- |
| `opencode: command not found` | Add `~/go/bin` to your PATH |
| Go not found | Install Go ≥ 1.21 first |
| API key error | Set the correct env variable for your provider |
| TUI not rendering | Use a modern terminal (Windows Terminal, iTerm2) |

---

> 📌 **Official Repo**: [github.com/opencode-ai/opencode](https://github.com/opencode-ai/opencode)
