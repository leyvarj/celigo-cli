# Installation (macOS)

## Requirements

- [Node.js 22+](https://nodejs.org/en)

Node.js includes npm by default.

## Installation

```bash
npm install -g @celigo/celigo-cli
```

Verify installation:

```bash
celigo --version
```

## Post-installation Behavior

Installing Celigo CLI also registers AI assistant skills for supported coding
assistants.

## AI Assistant Skill Locations

- [Opencode](https://opencode.ai)
  - `~/.config/opencode/skills/` (global)

- [Claude Code](https://claude.com/product/claude-code)
  - `~/.claude/skills/` (global)

- Cursor / Windsurf / JetBrains:
  - location may vary depending on IDE configuration

---

## Related Documentation

- [Skills Not Loaded](../troubleshooting/skills-not-loaded.md)
