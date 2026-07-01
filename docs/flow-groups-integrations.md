# Manage Flow Groups

List, create, and delete flow groups within an integration.

List flow groups:

```bash
celigo integrations flow-groups <id>
```

Create a flow group:

```bash
celigo integrations create-flow-group <id> <name>
```

```bash
celigo integrations create-flow-group 5f83a9b2c7d3e8f1a2b3c4d5 "Inbound orders"
```

Delete a flow group (flows in it become ungrouped):

```bash
celigo integrations delete-flow-group <id> <flowGroupingId> [--yes]
```

**Arguments**

| Argument           | Type   | Required | Description                       |
| ------------------ | ------ | -------- | --------------------------------- |
| `<id>`             | string | Yes      | Integration ID.                   |
| `<name>`           | string | Yes      | Display name for the new group.   |
| `<flowGroupingId>` | string | Yes      | Group `_id` (from `flow-groups`). |

Required for `create-flow-group` (`<name>`) and `delete-flow-group`
(`<flowGroupingId>`).

**Flags**

| Flag          | Type | Default | Description                              |
| ------------- | ---- | ------- | ---------------------------------------- |
| `-y`, `--yes` | bool | `false` | Skip confirmation (`delete-flow-group`). |

> **NOTE** Creating and deleting flow groups only defines the group on the
> integration. Assign flows to a group with `flows set-group`.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/commands/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
