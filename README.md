# 🖥️ Operating System, Tools & AI Agents Reference

A centralized, comprehensive collection of essential commands, references, and AI agent setup guides for various Operating Systems, development tools, and modern AI coding assistants. Designed for quick access to command-line utilities, system administration, version control, and AI-powered development workflows.

---

## 📌 Features

- **Categorized Reference**: Commands organized by OS (Linux, Mac, Windows) and Tools (Git).
- **Consolidated Documentation**: Detailed Markdown guides with tables and descriptions for every platform.
- **Security & Pentesting**: Comprehensive coverage of Kali Linux tools and techniques.
- **Package Management**: Deep dives into `apt`, `pacman`, `brew`, and PowerShell cmdlets.
- **Shell Scripting**: Dedicated resources for automation and scripting.
- **AI Agent Setup**: Step-by-step install guides for Claude, Gemini, Codex, OpenCode, and Blackbox AI — with exact commands for Windows, Linux, and macOS.

---

## 📂 Directory Structure

```text
├── 📂 Agent Setup Terminal/
│   ├── 📄 README.md                        # Overview, quick-ref table & setup order
│   ├── 📂 Terminal_Setup/
│   │   └── 📄 terminal_setup.md            # Shell environment setup (all platforms)
│   ├── 📂 VSCode_Terminal/
│   │   └── 📄 vscode_terminal.md           # AI agents + extensions inside VS Code
│   ├── 📂 Claude/
│   │   └── 📄 claude_setup.md              # Anthropic Claude Code CLI
│   ├── 📂 Gemini/
│   │   └── 📄 gemini_setup.md              # Google Gemini CLI
│   ├── 📂 OpenCode/
│   │   └── 📄 opencode_setup.md            # OpenCode multi-provider agent
│   ├── 📂 Blackbox/
│   │   └── 📄 blackbox_setup.md            # Blackbox AI (Terminal + VS Code)
│   └── 📂 Codex/
│       └── 📄 codex_setup.md               # OpenAI Codex CLI
├── 📂 Git/
│   └── 📄 git_commands.md                  # Version control quick reference
├── 📂 Linux/
│   ├── 📂 Arch_Commands/
│   │   └── 📄 arch_commands.md             # Pacman & AUR reference
│   ├── 📂 Kali_Commands/
│   │   └── 📄 kali_commands.md             # Penetration testing tools
│   └── 📂 Ubuntu_Commands/
│       ├── 📄 ubuntu_commands.md           # APT & Systemd management
│       └── 📂 Shell scripting/             # Automation & bash scripts
├── 📂 Mac/
│   └── 📄 mac_commands.md                  # macOS terminal & Homebrew
└── 📂 Windows/
    └── 📄 windows_commands.md              # CMD & PowerShell reference
```

---

## 🤖 AI Agent Quick Install Reference

| Agent | Install Command | Requires | API Key |
| :--- | :--- | :--- | :--- |
| **Claude Code** | `npm install -g @anthropic-ai/claude-code` | Node ≥ 18 | `ANTHROPIC_API_KEY` |
| **Gemini CLI** | `npm install -g @google/gemini-cli` | Node ≥ 18 | `GEMINI_API_KEY` (or Google login — free) |
| **Codex CLI** | `npm install -g @openai/codex` | Node ≥ 22 | `OPENAI_API_KEY` |
| **OpenCode** | `go install github.com/opencode-ai/opencode@latest` | Go ≥ 1.21 | Any provider key |
| **Blackbox CLI** | `npm install -g @blackboxapp/blackbox` | Node ≥ 16 | Free account |
| **Blackbox (VS Code)** | `code --install-extension Blackboxapp.blackbox` | VS Code | Free account |

> 💡 **New to AI agents?** Start with `Gemini CLI` — it's free with a Google account and needs no API key setup.

---

## 🚀 Getting Started

1. **Set up your terminal first** → See [`Agent Setup Terminal/Terminal_Setup/`](./Agent%20Setup%20Terminal/Terminal_Setup/terminal_setup.md)
2. **Pick your OS reference** → Open the `Linux/`, `Mac/`, or `Windows/` folder
3. **Pick an AI agent** → Open the corresponding folder inside `Agent Setup Terminal/`
4. **Follow the guide** → Each `.md` file has exact step-by-step commands
5. **Copy & run** → Paste commands directly into your terminal or shell

---

## 🛠️ Built With

- **Markdown** — Clean, structured, and readable documentation
- **Shell Scripting** — Custom scripts for automation in the Linux/Ubuntu section
- **Multi-platform Commands** — Windows (PowerShell/CMD), Linux (bash/zsh), macOS (zsh)

---

## 🎯 Purpose

This repository is a single-stop **cheat sheet** for developers, system administrators, and students to:

- Quickly find cross-platform terminal commands without searching external docs
- Set up AI coding agents (Claude, Gemini, Codex, Blackbox, OpenCode) with exact install commands
- Learn shell scripting, package management, and system administration across Linux, Mac, and Windows
