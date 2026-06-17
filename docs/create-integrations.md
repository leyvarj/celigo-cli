# Create Integrations

Create a project directory:

```bash
mkdir <integration_name> && cd <integration_name>
```

Create `integrations.json`:

```bash
touch integrations.json
vim integrations.json
```

> **NOTE** The JSON file must include `name` and `description`. Without both
> fields, the command will fail.

```json
{
  "name": "Salesforce AM Account Reporting",
  "description": "Contains flows that fetch Salesforce account records."
}
```

Then run:

```bash
celigo integrations create < integrations.json
```

`name` and `description` are required. All other fields are optional.

## Payload Anatomy

| Field                       | Type   | Required | Read-only | Description                            |
| --------------------------- | ------ | -------- | --------- | -------------------------------------- |
| `_id`                       | string | No       | Yes       | Server-assigned on creation.           |
| `name`                      | string | Yes      | No        | Human-readable name (max 100 chars).   |
| `description`               | string | Yes      | No        | Purpose and behavior (max 5120 chars). |
| `install`                   | array  | No       | No        | Install cards (Integration App).       |
| `_registeredLookupCacheIds` | array  | No       | Yes       | Platform-managed lookup caches.        |
| `installSteps`              | array  | No       | No        | Installation lifecycle steps.          |
| `uninstallSteps`            | array  | No       | No        | Uninstallation lifecycle steps.        |
| `changeEditionSteps`        | array  | No       | No        | Edition change steps.                  |
| `flowGroupings`             | array  | No       | No        | UI grouping sections for flows.        |
| `apiGroupings`              | array  | No       | No        | UI grouping sections for APIs.         |

> **NOTE** Read-only fields (`_id`, `_registeredLookupCacheIds`) are assigned by
> the platform and will be ignored on create or overwritten on update.

Full example, see:

- [integrations.json](../examples/integrations.json)

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
