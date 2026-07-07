# Register Connections

Register one or more connections to an integration.

```bash
celigo integrations register-connections <id> <connectionIds...>
```

```bash
celigo integrations register-connections 5f83a9b2c7d3e8f1a2b3c4d5 connA connB
```

**Arguments**

| Argument             | Type              | Required | Description                 |
| -------------------- | ----------------- | -------- | --------------------------- |
| `<id>`               | string            | Yes      | Integration ID.             |
| `<connectionIds...>` | string (variadic) | Yes      | One or more connection IDs. |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

> **NOTE** Connections must already exist before they can be registered. Use
> `celigo connections create` first if needed.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
