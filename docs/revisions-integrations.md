# Revisions Integrations

List all revisions (snapshots, pulls, pushes) for an integration:

```bash
celigo integrations revisions <id>
```

**Arguments**

| Argument | Type   | Required | Description     |
| -------- | ------ | -------- | --------------- |
| `<id>`   | string | Yes      | Integration ID. |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

> **NOTE** Revisions can be snapshots (point-in-time captures), pulls (changes
> pulled from an environment), or pushes (changes pushed to an environment). Use
> `revision-diff` to inspect pending revisions before applying them.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
