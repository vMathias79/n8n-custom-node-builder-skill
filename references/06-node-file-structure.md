# Node File Structure (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/reference/node-file-structure/
- Retrieved At (UTC): 2026-02-24T09:30:52Z
- Scope: Required files/directories and recommended modular layout.

## Scaffolding

n8n recommends using the `n8n-node` CLI tool to create the expected file structure:

```shell
npx @n8n/n8n-node create
```

This generates the correct package layout and wires up `package.json` automatically. Customize the scaffold as needed for more complex structures.

## Required Structure

Your package must include:

- `package.json`
- `nodes/`
  - required base file: `<NodeName>.node.ts`
  - recommended codex file: `<NodeName>.node.json`
- `credentials/`
  - required credentials file: `<NodeName>.credentials.ts`

## Recommended Modular Pattern

For non-trivial nodes, split logic into modules:

- `actions/` for resources and operations
  - Each sub-directory represents a resource and contains:
    - A resource description file: `<resourceName>.resource.ts` (or `index.ts`)
    - Operation files: `<operationName>.operation.ts` — each exports `description` and an `execute` function
- `methods/` for dynamic parameter helpers
- `transport/` for API communication helpers

## Versioning Considerations

If using full node versioning, add versioned directories and maintain a base entry file that sets default version.

## Package Scope Choices

n8n supports:

- one node per npm package
- multiple nodes in one package

If multiple nodes are present, keep each node in its own directory under `nodes/`.

## Companion References

- Codex metadata: `references/09-codex.md`
- Credentials: `references/08-credentials.md`
