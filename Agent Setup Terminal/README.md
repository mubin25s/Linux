# 🤖 Agent Setup Terminal

A comprehensive, step-by-step reference for setting up AI coding agents in your terminal, VS Code, and other development environments. Every guide includes **exact install commands** for Windows, Linux, and macOS.

---

## 📂 Folder Structure

```text
Agent Setup Terminal/
├── 📄 README.md                        ← You are here
├── 📂 Terminal_Setup/
│   └── 📄 terminal_setup.md            # General terminal environment setup
├── 📂 VSCode_Terminal/
│   └── 📄 vscode_terminal.md           # AI agents inside VS Code
├── 📂 Claude/
│   └── 📄 claude_setup.md              # Anthropic Claude Code CLI
├── 📂 Gemini/
│   └── 📄 gemini_setup.md              # Google Gemini CLI
├── 📂 OpenCode/
│   └── 📄 opencode_setup.md            # OpenCode multi-provider agent
├── 📂 Blackbox/
│   └── 📄 blackbox_setup.md            # Blackbox AI (Terminal + VS Code)
└── 📂 Codex/
    └── 📄 codex_setup.md               # OpenAI Codex CLI
```

---

## 📋 Quick Reference — Install Commands

| Agent | Install Command | API Key Env Var |
| :--- | :--- | :--- |
| **Claude Code** | `npm install -g @anthropic-ai/claude-code` | `ANTHROPIC_API_KEY` |
| **Gemini CLI** | `npm install -g @google/gemini-cli` | `GEMINI_API_KEY` |
| **Codex CLI** | `npm install -g @openai/codex` | `OPENAI_API_KEY` |
| **OpenCode** | `go install github.com/opencode-ai/opencode@latest` | Any provider key |
| **Blackbox CLI** | `npm install -g @blackboxapp/blackbox` | Account login |
| **Blackbox (VS Code)** | `code --install-extension Blackboxapp.blackbox` | Account login |

---

## 🗂️ Guide Details

### 🖥️ [Terminal Setup](./Terminal_Setup/terminal_setup.md)
> **Best starting point** — set up your terminal environment before installing any agent.

- Install Windows Terminal, PowerShell 7, Scoop / Chocolatey
- Install Zsh + Oh My Zsh on Linux & macOS
- Configure Node.js, Python, Git on all platforms
- Set environment variables (API keys) permanently
- Useful shell aliases for AI agents

---

### 🖊️ [VS Code Terminal](./VSCode_Terminal/vscode_terminal.md)
> Run AI agents inside VS Code's integrated terminal + install AI extensions.

- Install VS Code on Windows / Linux / macOS
- Configure the integrated terminal shell
- Install extensions: **GitHub Copilot**, **Blackbox**, **Continue.dev**, **Gemini Code Assist**, **Codeium**
- Set API keys via `settings.json`
- VS Code keyboard shortcuts & recommended settings

---

### 🤖 [Claude](./Claude/claude_setup.md)
> **Anthropic's Claude Code** — powerful coding agent with deep project understanding.

```bash
npm install -g @anthropic-ai/claude-code
claude
```

- Covers: install → API key → auth → usage
- Platforms: Windows, Linux, macOS
- Key flag: `--model claude-opus-4-5`

---

### 💎 [Gemini](./Gemini/gemini_setup.md)
> **Google Gemini CLI** — open-source agent, free tier with Google login (no API key needed).

```bash
npm install -g @google/gemini-cli
gemini
```

- Covers: install → Google OAuth or API key → usage
- Platforms: Windows, Linux, macOS
- Key flag: `--model gemini-2.5-pro`

---

### 🟢 [Codex](./Codex/codex_setup.md)
> **OpenAI Codex CLI** — lightweight agent with `suggest`, `auto-edit`, and `full-auto` modes.

```bash
npm install -g @openai/codex
codex
```

- Covers: install → API key → approval modes → usage
- Requires: Node.js ≥ 22, paid OpenAI account
- Key flag: `--approval-mode full-auto`

---

### 📦 [OpenCode](./OpenCode/opencode_setup.md)
> **OpenCode** — multi-provider TUI agent supporting OpenAI, Anthropic, Gemini, and Ollama.

```bash
go install github.com/opencode-ai/opencode@latest
opencode
```

- Covers: install (Go / npm / binary) → provider setup → usage
- Supports: OpenAI, Claude, Gemini, Ollama (local/free)
- Key flag: `--model anthropic/claude-opus-4-5`

---

### ⬛ [Blackbox](./Blackbox/blackbox_setup.md)
> **Blackbox AI** — terminal chat + VS Code autocomplete + command suggestions.

```bash
# CLI
npm install -g @blackboxapp/blackbox

# VS Code Extension
code --install-extension Blackboxapp.blackbox
```

- Covers: CLI install → VS Code extension → login → usage
- Free account available at [blackbox.ai](https://blackbox.ai)

---

## ⚙️ Common Prerequisites

Before installing any agent, ensure these are installed:

```bash
# 1. Check Node.js (required for Claude, Gemini, Codex, Blackbox)
node --version    # Need ≥ 18 (≥ 22 for Codex)

# 2. Check npm
npm --version     # Need ≥ 8

# 3. Check Go (required for OpenCode)
go version        # Need ≥ 1.21

# 4. Check Git
git --version
```

### Install Node.js quickly:

| Platform | Command |
| :--- | :--- |
| Windows | `winget install OpenJS.NodeJS` |
| Ubuntu/Debian | `curl -fsSL https://deb.nodesource.com/setup_20.x \| sudo -E bash - && sudo apt-get install -y nodejs` |
| macOS | `brew install node` |

---

## 🔑 API Keys — Where to Get Them

| Agent | API Key URL | Starts With |
| :--- | :--- | :--- |
| Claude | [console.anthropic.com](https://console.anthropic.com) | `sk-ant-...` |
| Gemini | [aistudio.google.com/apikey](https://aistudio.google.com/apikey) | `AIza...` |
| Codex | [platform.openai.com/api-keys](https://platform.openai.com/api-keys) | `sk-...` |
| OpenCode | Any of the above | Depends on provider |
| Blackbox | [blackbox.ai](https://blackbox.ai) (free login) | N/A |

### Set API keys permanently:

**Windows (PowerShell)**
```powershell
[System.Environment]::SetEnvironmentVariable("ANTHROPIC_API_KEY", "sk-ant-...", "User")
[System.Environment]::SetEnvironmentVariable("OPENAI_API_KEY", "sk-...", "User")
[System.Environment]::SetEnvironmentVariable("GEMINI_API_KEY", "AIza-...", "User")
```

**Linux / macOS**
```bash
echo 'export ANTHROPIC_API_KEY="sk-ant-..."' >> ~/.bashrc
echo 'export OPENAI_API_KEY="sk-..."' >> ~/.bashrc
echo 'export GEMINI_API_KEY="AIza-..."' >> ~/.bashrc
source ~/.bashrc
```

---

## 🚀 Recommended Setup Order

```
1. Terminal_Setup  →  Set up your shell environment first
2. VSCode_Terminal →  Configure VS Code if you use it
3. Pick an agent   →  Claude / Gemini / Codex / OpenCode / Blackbox
```

---

> 💡 **New to AI agents?** Start with **Gemini CLI** — it's free with a Google account and needs no API key.
> 💡 **Best for coding?** Try **Claude Code** (`claude`) or **OpenAI Codex** (`codex`).
