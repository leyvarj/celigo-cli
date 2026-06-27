# Update Integrations

Modify an existing integration.

## Update (PUT Replace)

Full PUT replace from a JSON body. Omitted fields are erased.

```bash
celigo integrations update <id> --file <path>
```

Pipe from a `get` + `jq` to make a single change without losing fields:

```bash
celigo integrations get 5f83a9b2c7d3e8f1a2b3c4d5 --format json \
  | jq '.name = "renamed"' \
  | celigo integrations update 5f83a9b2c7d3e8f1a2b3c4d5
```

**Arguments**

| Argument | Type   | Required | Description     |
| -------- | ------ | -------- | --------------- |
| `<id>`   | string | Yes      | Integration ID. |

**Flags**

| Flag                  | Type   | Default | Description                                                      |
| --------------------- | ------ | ------- | ---------------------------------------------------------------- |
| `-f`, `--file <path>` | string | —       | Read the JSON body from a file (`--file -` reads from stdin).    |
| `--force`             | bool   | `false` | Submit even if the body contains `***` masked credential values. |

> **NOTE** `update` is a full PUT replace. Any field not included in the body is
> erased. Always round-trip through `get` + `jq` instead of writing a body from
> scratch. Use `set` for targeted edits.

## Set (Safe Edit)

Whitelisted fields (`name`, `debugUntil`, `schedule.*`, etc.) are applied via
atomic PATCH. All other fields go through GET + modify + PUT. Values are
auto-parsed as JSON — `set disabled=true` produces a boolean, not a string.

```bash
celigo integrations set <id> key=value [key2=value2 ...]
```

```bash
celigo integrations set 5f83a9b2c7d3e8f1a2b3c4d5 'name=Shopify -> NetSuite (v2)'
```

Dot notation and array indexing are supported:

```bash
celigo integrations set 5f83a9b2c7d3e8f1a2b3c4d5 schedule.disabled=true
```

**Arguments**

| Argument                 | Type              | Required | Description                                                                   |
| ------------------------ | ----------------- | -------- | ----------------------------------------------------------------------------- |
| `<id>`                   | string            | Yes      | Integration ID.                                                               |
| `key=value` (repeatable) | string (variadic) | Yes      | One or more assignments. Use `key=file://<path>` to load a value from a file. |

**Flags**

_None beyond
[global flags](https://developer.celigo.com/cli/getting-started/global-flags.md)._

> **NOTE** `null` removes a field (`debugUntil=null`), `file://<path>` loads a
> file (JSON files parse to an object, everything else is a literal string), and
> if a value isn't valid JSON it falls back to the literal string.

## Related Documentation

- [Integrations CLI Reference](https://developer.celigo.com/cli/build/integrations)
- [Celigo Integrations API Reference](https://developer.celigo.com/api/api-reference/integrations)
