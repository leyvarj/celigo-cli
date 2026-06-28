# Audit Integrations

Show the change history for one integration.

```bash
celigo integrations audit <id>
```

Format the output as a table:

```bash
celigo integrations audit 5f83a9b2c7d3e8f1a2b3c4d5 --format table
```

**Arguments**

| Argument | Type   | Required | Description     |
| -------- | ------ | -------- | --------------- |
| `<id>`   | string | Yes      | Integration ID. |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
