# Clone Integrations

Clone an integration (and all child resources) into a target environment.

```bash
celigo integrations clone <id> <environmentId> [--name <name>]
```

Same-environment clones auto-build a self-map from the source integration's
`_registeredConnectionIds`. Cross-environment clones need an explicit
`connectionMap` piped via stdin:

```bash
echo '{"connectionMap":{"sourceConnId":"targetConnId"}}' \
  | celigo integrations clone 5f83a9b2c7d3e8f1a2b3c4d5 envABC
```

**Arguments**

| Argument          | Type   | Required | Description            |
| ----------------- | ------ | -------- | ---------------------- |
| `<id>`            | string | Yes      | Source integration ID. |
| `<environmentId>` | string | Yes      | Target environment ID. |

**Flags**

| Flag            | Type   | Default                 | Description                      |
| --------------- | ------ | ----------------------- | -------------------------------- |
| `--name <name>` | string | `Clone - <source name>` | Name for the cloned integration. |

> **NOTE** Only pipe a `connectionMap` on stdin when cloning across
> environments. Same-environment clones handle connection mapping automatically
> from `_registeredConnectionIds`.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
