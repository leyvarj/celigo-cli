# Download Integrations

Log in to integrator.io and copy the integration ID from the URL.

Then run:

> **NOTE** The `<id>` argument is a 24-character hex string assigned by the
> platform. Copy it from the integration page URL in integrator.io.

```bash
celigo integrations download 000000000000000000000001 -o ./backup.zip
```

**Arguments**

| Argument | Type   | Required | Description     |
| -------- | ------ | -------- | --------------- |
| `<id>`   | string | Yes      | Integration ID. |

**Flags**

| Flag                    | Type   | Default             | Description            |
| ----------------------- | ------ | ------------------- | ---------------------- |
| `-o`, `--output <path>` | string | `<name>.zip` in CWD | Destination file path. |

> **NOTE** Integration App installations (non-standalone integrations) cannot be
> downloaded. The command will reject them.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
