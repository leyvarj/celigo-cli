# CLI Commands Quick Reference

## Common Tasks

| Goal                        | Command                                                                         | Notes                                                                                                                                         |
| --------------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Install the CLI             | `npm install -g @celigo/celigo-cli`                                             | Requires Node.js 22+.                                                                                                                         |
| Authenticate with a token   | `export CELIGO_API_TOKEN="<paste>"`                                             | Or use `celigo profile add <name> --api-token "$TOKEN"`.                                                                                      |
| Set the default profile     | `celigo profile use us`                                                         |                                                                                                                                               |
| Show active profile config  | `celigo config show`                                                            | Shows `api_token` (redacted) and `default_format`.                                                                                            |
| One-off profile override    | `celigo --profile eu flows list`                                                | Combine `--profile <name>` with any command.                                                                                                  |
| See global flags            | `celigo --help`                                                                 | Includes `--profile`, `--format`, `--jq`, `--verbose`, `--token`, `--base-url`.                                                               |
| Pipe JSON output through jq | `celigo flows list --format json \| jq '.[] \| {_id, name}'`                    | Every command supports `--format json` and `--jq '<filter>'`.                                                                                 |
| Exit codes                  | See [Exit codes docs](https://developer.celigo.com/cli/reference/exit-codes.md) | `0` = success, `1` = error, `2` = invalid usage.                                                                                              |
| List users (table format)   | `celigo users list --format table`                                              | Columns: `_id`, `accessLevel`, `accepted`, `lastModified`.                                                                                    |
| List users with limit       | `celigo users list --limit 1 --format table`                                    | `--limit` is not supported on list commands; see [Unsupported `--limit` Flag](../troubleshooting/unsupported-limit-flag.md) for alternatives. |

## Full Reference

### Local (no REST API)

| Command        | Subcommands                                                            | Purpose                                                                  |
| -------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| `profile`      | list, show, use, add, delete, rename                                   | Manage named CLI profiles (credentials, region, mode).                   |
| `config`       | show, get, set                                                         | Read/write `~/.celigo/config.json` keys per profile.                     |
| `account`      | snapshot, search, deps, lint, stats                                    | Local index: fetch all resources, then search/depend/lint/count offline. |
| `account-info` | settings, profile, applications, processors, shared-accounts, discover | REST-backed read-only account metadata.                                  |

### Build

| Command         | Subcommands                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Purpose                                                                                         |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `integrations`  | list, get, create, update, set, delete, clone, flow-groups, flow-group-create, flow-group-assign, register-connections, deregister-connections, download, errors, assign-errors, revisions, revision, snapshot, revision-diff                                                                                                                                                                                                                                                                                                                      | Container CRUD, revision lifecycle, error triage, connection registration.                      |
| `flows`         | list, get, create, update, set, delete, run, clone, errors, resolved-errors, resolve-errors, error-request-detail, retry-errors, assign-errors, delete-resolved, error-data, update-error-data, tag-errors, error-summary, error-analyze, add-processor, remove-processor, add-generator, remove-generator, replace-connection, debug-requests, debug-request-detail, test-run, test-run-step, test-run-step-logs, execution-logs-enable, execution-logs-disable, execution-logs, execution-log-query, execution-log-data, last-export-date, trace | Full flow CRUD, error ops (resolve/retry/assign/tag), test runs, exec logs, per-record tracing. |
| `connections`   | list, get, create, update, delete, ping, debug-enable, debug-disable, debug-logs, authorize                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Connection CRUD, connectivity test, OAuth authorize flow, debug logging.                        |
| `exports`       | list, get, create, update, set, delete, clone, replace-connection, invoke, debug-enable, debug-disable                                                                                                                                                                                                                                                                                                                                                                                                                                             | Export CRUD, ad-hoc invoke (data preview), connection swap, debug.                              |
| `imports`       | list, get, create, update, set, delete, invoke, clone, replace-connection, debug-enable, debug-disable                                                                                                                                                                                                                                                                                                                                                                                                                                             | Import CRUD, ad-hoc invoke (dry-run records through mapping), debug.                            |
| `async-helpers` | list, get, create, update, set, delete                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | Polling configs for long-running API operations (SP-API, SF Bulk 2.0).                          |
| `scripts`       | list, get, create, update, set, delete, logs, debug-enable, debug-disable, debug-logs                                                                                                                                                                                                                                                                                                                                                                                                                                                              | JavaScript hook CRUD, execution log inspection, debug.                                          |

### Extend

| Command       | Subcommands                                                                                                                                                                         | Purpose                                                    |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| `tools`       | list, get, create, update, set, delete, add-processor, remove-processor, test-run, test-run-step, test-run-step-logs, debug-requests, debug-request-detail                          | Reusable building blocks with input/output contracts.      |
| `apis`        | list, get, create, update, set, delete, logs, log-detail, clone, add-processor, remove-processor, test-run, test-run-step, test-run-step-logs, debug-requests, debug-request-detail | Custom synchronous HTTP endpoints.                         |
| `mcp-servers` | list, get, create, update, set, delete                                                                                                                                              | MCP endpoints exposing tools/APIs to AI clients.           |
| `agents`      | list, get, create, update, set, delete, invoke, debug-enable, debug-disable, clone, replace-connection                                                                              | AI agent imports (LLM classify/extract/validate/generate). |
| `guardrails`  | list, get, create, update, set, delete, invoke, debug-enable, debug-disable, clone, replace-connection                                                                              | Safety/compliance checks (PII, moderation, AI evaluation). |

### Operate

| Command         | Subcommands                                                                                                                       | Purpose                                                               |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `jobs`          | get, list, current, cancel, diagnostics, files, download, purge-files, family, latest-flow, latest-integration, errors, run-stats | Flow execution history, monitoring, file downloads, error inspection. |
| `audit`         | list, download                                                                                                                    | Change-tracking log, CSV export.                                      |
| `notifications` | list, subscribe, unsubscribe                                                                                                      | Per-user email/webhook notification subscriptions.                    |
| `subscriptions` | licenses, usage, entitlement-usage, historical, api-usage                                                                         | Account licensing and entitlement consumption (read-only).            |

### Administer

| Command    | Subcommands                            | Purpose                                                        |
| ---------- | -------------------------------------- | -------------------------------------------------------------- |
| `users`    | list, get, update, set, delete, invite | Account user management (ashares), invitations, access levels. |
| `iclients` | list, get, create, update, delete      | Shared OAuth credential stores (app registrations).            |

### Infrastructure

| Command        | Subcommands                                                         | Purpose                                     |
| -------------- | ------------------------------------------------------------------- | ------------------------------------------- |
| `stacks`       | list, get, create, update, set, delete, system-token, recycle-token | On-premise bridge runtimes (server/Lambda). |
| `environments` | list, get, create, update, set                                      | Sandbox/production partitions.              |
| `opa`          | list, get, create, update, set, delete, display-token, change-token | On-premise agents (network gateway tunnel). |

### Data

| Command         | Subcommands                                                                         | Purpose                                                 |
| --------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------- |
| `lookup-caches` | list, get, create, update, set, delete, put-data, get-data, delete-data, purge-data | In-memory key-value stores for dedup/cross-ref/state.   |
| `tags`          | list, get, create, update, set, delete                                              | Short labels for filtering flows, errors, integrations. |

### B2B / EDI

| Command            | Subcommands                            | Purpose                                                      |
| ------------------ | -------------------------------------- | ------------------------------------------------------------ |
| `edi-profiles`     | list, get, create, update, set, delete | X12/EDIFACT envelope and transaction configs.                |
| `edi-transactions` | list                                   | Read-only EDI transaction log.                               |
| `file-definitions` | list, get, create, update, set, delete | Parsing/generation rules for fixed-width, CSV, X12, EDIFACT. |

### Discover

| Command           | Subcommands           | Purpose                                                    |
| ----------------- | --------------------- | ---------------------------------------------------------- |
| `http-connectors` | list, get, search     | Read-only catalog of 550+ HTTP connector definitions.      |
| `tp-connectors`   | list, get, search     | Read-only catalog of 590+ trading partner connectors.      |
| `templates`       | list, search, preview | Marketplace templates (blueprint preview, read-only).      |
| `metadata`        | types, fields         | Live metadata introspection (NetSuite, Salesforce, RDBMS). |

## Related Documentation

- [Celigo CLI | CLI | Celigo Developer Platform](https://developer.celigo.com/cli)
