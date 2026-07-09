# Snapshot Integrations

Create a snapshot revision of the current integration state.

```bash
celigo integrations create-snapshot <id> --description <text>
```

```bash
celigo integrations create-snapshot 5f83a9b2c7d3e8f1a2b3c4d5 \
  --description 'before holiday freeze'
```

**Arguments**

| Argument | Type   | Required | Description     |
| -------- | ------ | -------- | --------------- |
| `<id>`   | string | Yes      | Integration ID. |

**Flags**

| Flag                   | Type   | Default      | Description                          |
| ---------------------- | ------ | ------------ | ------------------------------------ |
| `--description <text>` | string | — (required) | Human-readable snapshot description. |

> **NOTE** `--description` is enforced by the CLI even though the API accepts an
> empty value. Completed snapshots are point-in-time captures — unlike pending
> revisions, they cannot be diffed.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
