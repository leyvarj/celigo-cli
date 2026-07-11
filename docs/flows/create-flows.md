# Create a Flow

Create a flow from a JSON body (stdin, or `--file`).

```bash
celigo flows create
```

Pipe a JSON payload:

```bash
cat flow.json | celigo flows create
```

Read from a file:

```bash
celigo flows create --file flow.json
```

**Arguments**

_None._

**Flags**

| Flag                | Type   | Required | Description                                                             |
| ------------------- | ------ | -------- | ----------------------------------------------------------------------- |
| `-f, --file <path>` | string | No       | Read the JSON body from a file instead of stdin (`-` also means stdin). |

> **NOTE** When no `--file` is provided, the CLI reads JSON from stdin. An error
> is thrown in an interactive terminal with no piped input.

## Related Documentation

- [Flows CLI Reference](https://developer.celigo.com/cli/build/flows)
- [Celigo Flows API Reference](https://developer.celigo.com/api/api-reference/flows)
