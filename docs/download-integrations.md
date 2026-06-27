# Download Integrations

Download an integration as a ZIP archive.

```bash
celigo integrations download 5f83a9b2c7d3e8f1a2b3c4d5 -o ./backup.zip
```

**Arguments**

| Argument | Type   | Required | Description                                                                        |
| -------- | ------ | -------- | ---------------------------------------------------------------------------------- |
| `<id>`   | string | Yes      | Integration ID (24-char hex). Copy from the integration page URL in integrator.io. |

**Flags**

| Flag                    | Type   | Default             | Description            |
| ----------------------- | ------ | ------------------- | ---------------------- |
| `-o`, `--output <path>` | string | `<name>.zip` in CWD | Destination file path. |

> **NOTE** Integration App installations (non-standalone integrations) cannot be
> downloaded. The command will reject them.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
