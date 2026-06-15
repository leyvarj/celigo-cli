# Skills Not Loaded

## Symptoms

Celigo CLI is installed successfully, but AI assistant skills are not registered
in:

- `~/.claude/skills/`
- `~/.config/opencode/skills/`

## Condition

Skill registration occurs only when supported directories exist during
installation.

The target skill directories did not exist at the time of installation.

Example:

- `~/.claude/` was not present during installation
- no skill registration occurred

## Resolution

### Option 1: [Install Claude Code](https://claude.com/product/claude-code) first, then reinstall

```bash
npm install -g @celigo/celigo-cli
```

### Option 2: Manually create required directories

```bash
mkdir -p ~/.claude/skills
```

Then reinstall:

```bash
npm install -g @celigo/celigo-cli
```

## Related Documentation

- [Installation](../docs/installation.md)
