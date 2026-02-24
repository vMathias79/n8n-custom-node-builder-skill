# Node UI Elements (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/reference/ui-elements/
- Retrieved At (UTC): 2026-02-24T09:30:52Z
- Scope: Parameter schema patterns and UI component selection.

## Core Field Shape

Common keys:

- `displayName`
- `name`
- `type`
- `required`
- `default`
- `description`
- `displayOptions`

Use `displayOptions.show/hide` to scope fields to specific resources/operations.

## Frequently Used Field Types

- `string` (including password via `typeOptions: { password: true }` and multiline via `typeOptions: { rows: N }`)
- `number` (supports `maxValue`, `minValue`, `numberPrecision` in `typeOptions`)
- `boolean`
- `color`
- `dateTime`
- `options`
- `multiOptions`
- `collection`
- `fixedCollection`
- `resourceLocator`
- `resourceMapper`
- `json`
- `notice`
- hints/dynamic hints
- `filter`
- `assignmentCollection` (drag-and-drop name/value mapping)

## Data Mapping UX

For drag-and-drop mapping support, use `requiresDataPath`:

- `single` for one value
- `multiple` for list-like mappings

## Practical Guidance

- Keep required inputs minimal.
- Push optional/advanced inputs into collections.
- Prefer `resourceLocator` where users may identify entities by ID/URL/list.
- Use `resourceMapper` when schema mapping is central to the operation.
- Keep parameter names and help text in clear English.
