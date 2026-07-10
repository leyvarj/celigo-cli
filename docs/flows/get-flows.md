# Get a Flow

Fetch a single flow by ID.

```bash
celigo flows get <id>
```

Pipe through `jq` to extract specific fields:

```bash
celigo flows get 5f83a9b2c7d3e8f1a2b3c4d5 --format json | jq '{name,schedule}'
```

**Arguments**

| Argument | Type   | Required | Description |
| -------- | ------ | -------- | ----------- |
| `<id>`   | string | Yes      | Flow ID.    |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

## Related Documentation

- [Flows CLI Reference](https://developer.celigo.com/cli/build/flows)
- [Celigo Flows API Reference](https://developer.celigo.com/api/api-reference/flows)
