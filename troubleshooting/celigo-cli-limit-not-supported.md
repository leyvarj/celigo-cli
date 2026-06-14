# `--limit` Not Supported

## Symptoms

```bash
celigo users list --limit 1 --format json
```

Returns:

```
error: unknown option '--limit'
```

## Condition

`--limit` is not a global flag and is not implemented on any `list` command. The
CLI auto-paginates and returns the full result set as one flat array.

## Resolution

Use `--jq` to take a slice of the result:

```bash
celigo users list --jq '.[0]'
```

For multiple items:

```bash
celigo users list --jq '.[0:5]'
```

## Related Documentation

- [Celigo CLI Commands](../docs/celigo-cli-commands.md)
