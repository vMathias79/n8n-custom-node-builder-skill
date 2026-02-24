# Submit Community Nodes (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/deploy/submit-community-nodes/
- Retrieved At (UTC): 2026-02-24T09:30:52Z
- Scope: Publishing and submission requirements for community node packages.

## Core Standards

- Package name starts with `n8n-nodes-` (or scoped `@<scope>/n8n-nodes-...`).
- Include `n8n-community-node-package` in keywords.
- Register nodes and credentials in `package.json` under `n8n`.
- Run local quality checks before publish (`npm run lint`, `npm run dev`).
- Publish package to npm registry.

## Verification Submission Requirements

Before Creator Portal submission:

- Use `n8n-node` CLI tool scaffolding (strongly recommended — required for verified nodes).
- Follow technical verification guidelines.
- Follow UX guidelines.
- Provide clear public documentation (README/API docs).
- Ensure npm package is available for vetting.
- **From May 1st 2026**: All community nodes must be published via a GitHub Action and include an [npm provenance statement](https://docs.npmjs.com/generating-provenance-statements).

## Submission Path

Use n8n Creator Portal:

- https://creators.n8n.io/nodes

## Related References

- `references/12-verification-guidelines.md`
- https://docs.n8n.io/integrations/creating-nodes/build/reference/ux-guidelines/
