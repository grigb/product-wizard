# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 📍 This is a REDIRECT File Only

**ALL project configuration is in AGENTS.md** - this file just helps Claude Code find it.

## 🚨 CRITICAL: AGENTS.md REQUIRED

**IF YOU ARE READING THIS, CHECK IF AGENTS.md EXISTS**

If AGENTS.md does NOT exist in this directory, you MUST:
1. Create AGENTS.md immediately
2. Reference global rules: `~/.agents/AGENTS.md`
3. Move all project configuration to AGENTS.md

## This File's Purpose
- **CLAUDE.md**: Just a pointer to find AGENTS.md
- **AGENTS.md**: Contains ALL actual rules and configuration

## Required Action
```bash
# Check if AGENTS.md exists
if [ ! -f "AGENTS.md" ]; then
  echo "ERROR: AGENTS.md is missing - creating it now"
  cat > AGENTS.md << 'EOF'
# Project AI Assistant Rules

**Global Rules**: This project follows the universal AI agent rules at `~/.agents/AGENTS.md`

## Project-Specific Configuration
[Project configuration goes here]
EOF
fi
```

**DO NOT PUT CONFIGURATION HERE** - All configuration belongs in AGENTS.md