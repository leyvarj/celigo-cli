# Revision Integrations

Get details of a single revision.

```bash
celigo integrations revision <id> <revisionId>
```

**Arguments**

| Argument       | Type   | Required | Description     |
| -------------- | ------ | -------- | --------------- |
| `<id>`         | string | Yes      | Integration ID. |
| `<revisionId>` | string | Yes      | Revision ID.    |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

> **NOTE** Use `revisions` to list all revisions first, then pass the desired
> revision ID to `revision` for full details. Pending revisions (pulls, reverts)
> can also be inspected with `revision-diff`.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
