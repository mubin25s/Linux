# 🖊️ VS Code Terminal — AI Agent Setup Guide

This guide covers setting up and using AI coding agents directly inside VS Code's integrated terminal, including extensions, settings, and workflows.

---

## ✅ Prerequisites

| Requirement | Version | Check Command |
| :--- | :--- | :--- |
| VS Code | ≥ 1.85 | `code --version` |
| Node.js | ≥ 18.0 | `node --version` |
| Git | Any | `git --version` |

---

## 🪟 Step 1 — Install VS Code

### Windows
```powershell
winget install Microsoft.VisualStudioCode

# Verify
code --version
```

### Linux (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install -y wget gpg

wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/

sudo sh -c 'echo "deb [arch=amd64 signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] \
  https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

sudo apt update
sudo apt install -y code

code --version
```

### macOS
```bash
brew install --cask visual-studio-code
code --version
```

---

## ⚙️ Step 2 — Configure VS Code Integrated Terminal

### Set Default Shell

**Windows — use PowerShell 7**
1. Open VS Code
2. Press `Ctrl+Shift+P` → type `Terminal: Select Default Profile`
3. Select **PowerShell** or **Git Bash**

**OR via settings.json:**
```json
{
  "terminal.integrated.defaultProfile.windows": "PowerShell",
  "terminal.integrated.defaultProfile.linux": "bash",
  "terminal.integrated.defaultProfile.osx": "zsh"
}
```

### Open Settings JSON
```
Ctrl+Shift+P → "Open User Settings (JSON)"
```

---

## 📦 Step 3 — Install AI Extensions in VS Code

### GitHub Copilot (OpenAI-powered)
```bash
code --install-extension GitHub.copilot
code --install-extension GitHub.copilot-chat
```

### Blackbox AI
```bash
code --install-extension Blackboxapp.blackbox
```

### Google Gemini Code Assist
```bash
code --install-extension GoogleCloudTools.cloudcode
```

### Continue.dev (Multi-model: Claude, GPT, Gemini, Ollama)
```bash
code --install-extension Continue.continue
```

### Codeium (Free AI Autocomplete)
```bash
code --install-extension Codeium.codeium
```

### List all installed extensions
```bash
code --list-extensions
```

---

## 🚀 Step 4 — Run AI CLI Agents in VS Code Terminal

Open the integrated terminal: `` Ctrl+` `` (backtick)

### Run Claude Code
```bash
npm install -g @anthropic-ai/claude-code
claude
```

### Run Gemini CLI
```bash
npm install -g @google/gemini-cli
gemini
```

### Run OpenAI Codex CLI
```bash
npm install -g @openai/codex
codex
```

### Run OpenCode
```bash
go install github.com/opencode-ai/opencode@latest
opencode
```

---

## ⚙️ Step 5 — Set API Keys in VS Code Terminal

### Windows (PowerShell terminal in VS Code)
```powershell
# Set permanently for all sessions
[System.Environment]::SetEnvironmentVariable("ANTHROPIC_API_KEY", "sk-ant-...", "User")
[System.Environment]::SetEnvironmentVariable("OPENAI_API_KEY", "sk-...", "User")
[System.Environment]::SetEnvironmentVariable("GEMINI_API_KEY", "AIza-...", "User")

# Restart VS Code terminal after setting
```

### Linux / macOS (bash/zsh terminal in VS Code)
```bash
echo 'export ANTHROPIC_API_KEY="sk-ant-..."' >> ~/.bashrc
echo 'export OPENAI_API_KEY="sk-..."' >> ~/.bashrc
echo 'export GEMINI_API_KEY="AIza-..."' >> ~/.bashrc
source ~/.bashrc
```

### Add to VS Code settings.json (terminal env vars)
```json
{
  "terminal.integrated.env.windows": {
    "ANTHROPIC_API_KEY": "sk-ant-your-key",
    "OPENAI_API_KEY": "sk-your-key",
    "GEMINI_API_KEY": "AIza-your-key"
  },
  "terminal.integrated.env.linux": {
    "ANTHROPIC_API_KEY": "sk-ant-your-key",
    "GEMINI_API_KEY": "AIza-your-key"
  }
}
```

> ⚠️ Avoid storing real keys in `settings.json` if the file is shared or committed to git.

---

## ⌨️ Useful VS Code Terminal Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `` Ctrl+` `` | Toggle integrated terminal |
| `Ctrl+Shift+\`` | Create new terminal |
| `Ctrl+Shift+5` | Split terminal |
| `Ctrl+PgUp / PgDn` | Switch between terminals |
| `Ctrl+K` | Clear terminal |
| `Alt+Click` | Move cursor to clicked position |

---

## 💡 Recommended VS Code Settings for AI Workflows

Add to your `settings.json` (`Ctrl+Shift+P` → *Open User Settings JSON*):

```json
{
  "editor.inlineSuggest.enabled": true,
  "editor.suggest.preview": true,
  "editor.acceptSuggestionOnEnter": "smart",
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.fontFamily": "CaskaydiaCove Nerd Font, Consolas, monospace",
  "terminal.integrated.scrollback": 10000,
  "terminal.integrated.persistentSessionSupport": true,
  "github.copilot.enable": {
    "*": true
  }
}
```

---

## 🔄 Update All AI Extensions

```bash
# Update all extensions at once
code --install-extension GitHub.copilot --force
code --install-extension Continue.continue --force
code --install-extension Blackboxapp.blackbox --force
```

---

## ❗ Troubleshooting

| Problem | Fix |
| :--- | :--- |
| Terminal can't find `claude` / `gemini` | Restart VS Code after installing CLI tools |
| API key not found in terminal | Add to `terminal.integrated.env` in settings |
| Extension not activating | Press `Ctrl+Shift+P` → *Reload Window* |
| Terminal slow to start | Reduce shell startup scripts in `.bashrc` / `.zshrc` |
| `code` command not found (macOS) | Run `Shell Command: Install 'code' command in PATH` from `Ctrl+Shift+P` |

---

> 📌 **VS Code Download**: [code.visualstudio.com](https://code.visualstudio.com)
> 📌 **VS Code Extensions Marketplace**: [marketplace.visualstudio.com](https://marketplace.visualstudio.com)
