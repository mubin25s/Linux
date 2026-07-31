# 🖥️ Terminal Setup — General AI Agent Environment Guide

This guide covers setting up a proper terminal environment for running AI coding agents on Windows, Linux, and macOS — including tools, shell configuration, and best practices.

---

## 🪟 Windows — Terminal Setup

### Step 1: Install Windows Terminal (Recommended)
```powershell
winget install Microsoft.WindowsTerminal

# Or from Microsoft Store: search "Windows Terminal"
```

### Step 2: Install PowerShell 7+ (Modern Shell)
```powershell
winget install Microsoft.PowerShell

# Verify
pwsh --version
```

### Step 3: Install Scoop (Package Manager for Windows)
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression

# Verify
scoop --version
```

### Step 4: Install Chocolatey (Alternative Package Manager)
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

choco --version
```

### Step 5: Install Node.js (Required for most AI CLIs)
```powershell
winget install OpenJS.NodeJS
# OR
scoop install nodejs
# OR
choco install nodejs

node --version
npm --version
```

### Step 6: Install Git
```powershell
winget install Git.Git
git --version
```

### Step 7: Set up Oh My Posh (Beautiful prompt)
```powershell
winget install JanDeDobbeleer.OhMyPosh
oh-my-posh init pwsh | Invoke-Expression
```

---

## 🐧 Linux (Ubuntu/Debian) — Terminal Setup

### Step 1: Update System
```bash
sudo apt update && sudo apt upgrade -y
```

### Step 2: Install Essential Tools
```bash
sudo apt install -y \
  curl \
  wget \
  git \
  build-essential \
  unzip \
  zip \
  htop \
  tree \
  jq
```

### Step 3: Install Node.js 20
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs

node --version
npm --version
```

### Step 4: Install Zsh + Oh My Zsh (Recommended shell)
```bash
# Install Zsh
sudo apt install -y zsh

# Install Oh My Zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Set Zsh as default shell
chsh -s $(which zsh)
```

### Step 5: Install useful Zsh plugins
```bash
# Syntax highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git \
  ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions \
  ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Add to ~/.zshrc
# plugins=(git zsh-syntax-highlighting zsh-autosuggestions)
```

### Step 6: Install Python (for Python-based agents)
```bash
sudo apt install -y python3 python3-pip python3-venv
python3 --version
pip3 --version
```

---

## 🍎 macOS — Terminal Setup

### Step 1: Install Homebrew (Package Manager)
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew --version
```

### Step 2: Install Essential Tools
```bash
brew install \
  git \
  curl \
  wget \
  node \
  python \
  jq \
  tree \
  htop
```

### Step 3: Install Zsh + Oh My Zsh
```bash
# Zsh is default on macOS — just install Oh My Zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Step 4: Install iTerm2 (Better terminal for macOS)
```bash
brew install --cask iterm2
```

---

## 🌍 Setting Environment Variables (API Keys)

Storing API keys safely across sessions:

### Windows (PowerShell — permanent)
```powershell
# Set for current user
[System.Environment]::SetEnvironmentVariable("OPENAI_API_KEY", "sk-...", "User")
[System.Environment]::SetEnvironmentVariable("ANTHROPIC_API_KEY", "sk-ant-...", "User")
[System.Environment]::SetEnvironmentVariable("GEMINI_API_KEY", "AIza-...", "User")

# Verify
echo $env:OPENAI_API_KEY
```

### Linux / macOS (permanent via shell profile)
```bash
# Add to ~/.bashrc or ~/.zshrc
cat >> ~/.bashrc << 'EOF'
export OPENAI_API_KEY="sk-your-key"
export ANTHROPIC_API_KEY="sk-ant-your-key"
export GEMINI_API_KEY="AIza-your-key"
EOF

source ~/.bashrc
```

### Use a `.env` file (per-project)
```bash
# Create .env in project root
echo 'OPENAI_API_KEY=sk-your-key' >> .env
echo 'ANTHROPIC_API_KEY=sk-ant-your-key' >> .env

# Load it in shell
export $(grep -v '^#' .env | xargs)
```

> ⚠️ **Always add `.env` to your `.gitignore` to avoid leaking API keys!**

---

## 🔧 Useful Terminal Aliases for AI Agents

Add these to your `~/.bashrc` or `~/.zshrc`:

```bash
# AI Agent shortcuts
alias ai-claude="claude"
alias ai-gemini="gemini"
alias ai-codex="codex"
alias ai-open="opencode"

# Quick project start with agent
alias dev-claude="cd ~/projects && claude"
alias dev-gemini="cd ~/projects && gemini"
```

---

## ✅ Final Checklist

| Tool | Installed | Version Check |
| :--- | :--- | :--- |
| Node.js ≥ 18 | ☐ | `node --version` |
| npm ≥ 8 | ☐ | `npm --version` |
| Git | ☐ | `git --version` |
| Python 3 | ☐ | `python3 --version` |
| API Keys set | ☐ | `echo $OPENAI_API_KEY` |
| Modern terminal | ☐ | Windows Terminal / iTerm2 / Zsh |

---

> 💡 Once your terminal is set up, install any AI agent from the sibling folders (Claude, Gemini, Codex, etc.).
