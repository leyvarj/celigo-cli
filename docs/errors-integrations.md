# Errors Integrations

Inspect every open error across all flows in an integration, or reassign them to
a user by email.

List all open errors:

```bash
celigo integrations errors <id>
```

Assign specific errors by ID:

```bash
celigo integrations assign-errors <id> <email> [errorIds]
```

Assign all open errors:

```bash
celigo integrations assign-errors <id> <email> [--yes]
```

**Arguments**

| Argument     | Type   | Required | Description                                                                |
| ------------ | ------ | -------- | -------------------------------------------------------------------------- |
| `<id>`       | string | Yes      | Integration ID (24-char hex).                                              |
| `<email>`    | string | Yes      | Target user's email.                                                       |
| `[errorIds]` | string | No       | Comma-separated error IDs. Omit to assign all open errors (requires `-y`). |

**Flags**

| Flag          | Type | Default | Description                                       |
| ------------- | ---- | ------- | ------------------------------------------------- |
| `-y`, `--yes` | bool | `false` | Skip confirmation when assigning all open errors. |

> **NOTE** Omitting `[errorIds]` assigns every open error in the integration.
> Specify individual IDs to avoid unintended bulk reassignment.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
