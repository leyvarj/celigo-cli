# Celigo CLI Skills Not Loaded

## Context

Installed Celigo CLI before Claude Code.

## Issue

Skills not appearing in `.claude/skills/` or `~/.config/opencode/skills/`.

## Observation

Celigo CLI was installed before Claude Code.

At the time of installation, the `~/.claude/` directory did not exist and no
skills were installed.

## Hypothesis

The Celigo CLI may expect the `~/.claude/` directory to exist before
installation so that skills can be registered automatically.

## Resolution

Install Claude Code, then re-run installation:

```bash
npm install -g @celigo/celigo-cli
```

## Alternative

Create the required directory manually:

```bash
mkdir -p ~/.claude/skills
```

Then re-run the Celigo CLI installation:

```bash
npm install -g @celigo/celigo-cli
```

## Related Documentation

- [Celigo CLI Installation](../docs/celigo-cli-installation.md)
