# Celigo CLI Configuration

Celigo CLI uses a two-level configuration model:

1. Authentication scope (shell or persistent config)
2. Context layer (profiles and regions)

API tokens are issued via [Integrator.io](https://integrator.io/signin).

## Shell-based Authentication (Ephemeral)

```bash
export CELIGO_API_TOKEN="<api_token>"
```

Authentication is scoped to the current shell session. The token is not
persisted.

## File-based Configuration (Persistent)

```bash
celigo config set api_token "<api_token>"
```

This initializes or updates the persistent configuration at:

```bash
~/.celigo/config.json
```

Default permissions are 0600 on Unix systems (macOS and Linux).

### Base Configuration

```json
{
  "active_profile": "default",
  "profiles": {
    "default": {
      "api_token": "<api_token>"
    }
  }
}
```

### Profiles (Identity Contexts)

```json
{
  "active_profile": "prod",
  "profiles": {
    "prod": {
      "api_token": "<token>"
    },
    "sandbox": {
      "api_token": "<token>"
    }
  }
}
```

### Regions (Routing Contexts)

```json
{
  "regions": {
    "us": {
      "base_url": "https://api.integrator.io"
    },
    "eu": {
      "base_url": "https://api.eu.integrator.io"
    }
  }
}
```

Profiles and regions are independent. A `prod` profile can route through `us` or
`eu`, and a `sandbox` profile can use a different region entirely.

### Configuration File Access

```bash
vim ~/.celigo/config.json
```

```bash
code ~/.celigo/config.json
```

### Runtime Behavior

Configuration changes are applied on the next CLI command execution.

### Output Format

The default output format for CLI commands is configurable:

```bash
celigo config set default_format table
```

Options are **json** (default) and **table**.

Or edit `~/.celigo/config.json` directly:

```json
{
  "active_profile": "default",
  "profiles": {
    "default": {
      "api_token": "<api_token>",
      "default_format": "table"
    }
  }
}
```

Resolution order (each overrides the next):

1. `--format` flag
2. `CELIGO_FORMAT` environment variable
3. `default_format` in `~/.celigo/config.json`
4. Built-in default: `json`

| Format  | Pros                                         | Cons                      |
| ------- | -------------------------------------------- | ------------------------- |
| `json`  | Full data, pipeable to `jq`, script-friendly | Verbose for human reading |
| `table` | Human-readable, easy to scan                 | Fields may be truncated   |

## Related Documentation

- [Celigo CLI Commands](../docs/celigo-cli-commands.md)
