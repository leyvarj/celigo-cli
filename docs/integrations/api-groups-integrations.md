# Manage API Groups

List, create, and delete API groups within an integration.

List API groups:

```bash
celigo integrations api-groups <id>
```

Create an API group:

```bash
celigo integrations create-api-group <id> <name>
```

```bash
celigo integrations create-api-group 5f83a9b2c7d3e8f1a2b3c4d5 "Public endpoints"
```

Delete an API group (APIs in it become ungrouped):

```bash
celigo integrations delete-api-group <id> <apiGroupingId> [--yes]
```

**Arguments**

| Argument          | Type   | Required | Description                      |
| ----------------- | ------ | -------- | -------------------------------- |
| `<id>`            | string | Yes      | Integration ID.                  |
| `<name>`          | string | Yes      | Display name for the new group.  |
| `<apiGroupingId>` | string | Yes      | Group `_id` (from `api-groups`). |

Required for `create-api-group` (`<name>`) and `delete-api-group`
(`<apiGroupingId>`).

**Flags**

| Flag          | Type | Default | Description                             |
| ------------- | ---- | ------- | --------------------------------------- |
| `-y`, `--yes` | bool | `false` | Skip confirmation (`delete-api-group`). |

> **NOTE** Creating and deleting API groups only defines the group on the
> integration. Assign APIs to a group with `apis set-group`.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/commands/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
