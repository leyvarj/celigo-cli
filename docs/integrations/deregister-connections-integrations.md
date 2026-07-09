# Deregister Connections

Deregister one or more connections from an integration.

```bash
celigo integrations deregister-connections <id> <connectionIds...> [--yes]
```

```bash
celigo integrations deregister-connections 5f83a9b2c7d3e8f1a2b3c4d5 connA connB --yes
```

**Arguments**

| Argument             | Type              | Required | Description                 |
| -------------------- | ----------------- | -------- | --------------------------- |
| `<id>`               | string            | Yes      | Integration ID.             |
| `<connectionIds...>` | string (variadic) | Yes      | One or more connection IDs. |

**Flags**

| Flag          | Type | Default | Description                               |
| ------------- | ---- | ------- | ----------------------------------------- |
| `-y`, `--yes` | bool | `false` | Skip the interactive confirmation prompt. |

> **NOTE** Deregistering removes the connection from the integration but does
> not delete the connection itself. Flows using the deregistered connection may
> break until reassigned.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
