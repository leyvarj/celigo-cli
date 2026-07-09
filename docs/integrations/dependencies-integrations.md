# Dependencies Integrations

List resources that depend on this integration.

```bash
celigo integrations dependencies <id>
```

Aliased as `used-by`:

```bash
celigo integrations used-by 5f83a9b2c7d3e8f1a2b3c4d5
```

**Arguments**

| Argument | Type   | Required | Description     |
| -------- | ------ | -------- | --------------- |
| `<id>`   | string | Yes      | Integration ID. |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

> **NOTE** An empty result means no resources depend on this integration,
> making it safe to delete. Always run `dependencies` before `delete` to
> avoid breaking downstream resources.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
