# Celigo CLI Installation (macOS)

## Requirements

- [Node.js 22+](https://nodejs.org/en)

Node.js includes npm as part of its default installation.

## Installation

```bash
npm install -g @celigo/celigo-cli
```

Verify installation:

```bash
celigo --version
```

Installing the Celigo CLI globally also sets up AI assistant skills for
supported coding assistants, including Claude Code, Cursor, and Windsurf.

These skills help AI assistants provide more accurate and context-aware answers
about integrator.io.

Common filesystem locations for AI assistant skills:

> **NOTE**: This guide does not cover IDE-specific skill locations, as I have
> not personally tested skill loading in VS Code, Cursor, Windsurf, or JetBrains
> IDEs.

- [Opencode](https://opencode.ai)
  - `~/.config/opencode/skills/` (global)

- [Claude Code](https://claude.com/product/claude-code)
  - `~/.claude/skills/` (global)

> **TROUBLESHOOTING**: If skills do not appear after installation, see:
> [Celigo CLI Skills Not Loaded](../troubleshooting/celigo-cli-skills-not-loaded.md)
