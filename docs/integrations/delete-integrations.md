# Delete Integrations

Delete an integration by ID.

```bash
celigo integrations delete <id> [--yes]
```

```bash
celigo integrations delete 5f83a9b2c7d3e8f1a2b3c4d5 --yes
```

**Arguments**

| Argument | Type   | Required | Description     |
| -------- | ------ | -------- | --------------- |
| `<id>`   | string | Yes      | Integration ID. |

**Flags**

| Flag          | Type | Default | Description                               |
| ------------- | ---- | ------- | ----------------------------------------- |
| `-y`, `--yes` | bool | `false` | Skip the interactive confirmation prompt. |

> **NOTE** Run `dependencies` first to check that no resources depend on this
> integration before deleting.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
