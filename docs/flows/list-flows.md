# List Flows

List all flows in the account.

```bash
celigo flows list
```

Filter by integration:

```bash
celigo flows list --integration 5f83a9b2c7d3e8f1a2b3c4d5
```

Format the output as a table:

```bash
celigo flows list --format table
```

**Arguments**

_None._

**Flags**

| Flag                 | Type   | Required | Description                                    |
| -------------------- | ------ | -------- | ---------------------------------------------- |
| `--integration <id>` | string | No       | List only flows belonging to this integration. |

> **NOTE** Default output format is JSON. Use `--format table` for a tabular
> view.

## Related Documentation

- [Flows CLI Reference](https://developer.celigo.com/cli/build/flows)
- [Celigo Flows API Reference](https://developer.celigo.com/api/api-reference/flows)
