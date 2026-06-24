# Revision Diff Integrations

Show the before/after diff for a pending revision:

```bash
celigo integrations revision-diff <id> <revisionId>
```

**Arguments**

| Argument       | Type   | Required | Description     |
| -------------- | ------ | -------- | --------------- |
| `<id>`         | string | Yes      | Integration ID. |
| `<revisionId>` | string | Yes      | Revision ID.    |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

> **NOTE** Only pending revisions (e.g. `pull` or `revert`) can be diffed.
> Completed snapshots are point-in-time captures and have no diff available.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
