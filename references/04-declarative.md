# Build Declarative-Style Node (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/declarative-style-node/
- Retrieved At (UTC): 2026-02-24T09:30:52Z
- Scope: Practical declarative build flow, required files, and packaging details.

## Prerequisites

- git
- Node.js + npm (Node 18.17.0 minimum in docs snippets)
- JavaScript/TypeScript and REST API basics

## Setup Flow

1. Start from n8n node starter or equivalent generated scaffold.
2. Remove example nodes/credentials from template.
3. Create required files:
   - `nodes/<NodeName>/<NodeName>.node.ts`
   - `nodes/<NodeName>/<NodeName>.node.json`
   - `credentials/<NodeName>Api.credentials.ts`
4. Install dependencies (`npm i`).

## Implementation Focus

- Import `NodeConnectionTypes` from `n8n-workflow` for `inputs`/`outputs` fields.
- Define resources/operations declaratively in node description.
- Set `usableAsTool: true` in description to allow AI agent tool use.
- Prefer `routing`-based request mapping rather than custom `execute()` logic.
- Keep optional fields in collections.
- Maintain clear `displayOptions` visibility rules.

## Icon Guidelines

- Prefer SVG icons; PNG icons must be 60×60px.
- Use `icon: 'file:<iconname>.svg'` in description.
- Do not reference Font Awesome directly — embed the image instead.

## Authentication + Metadata

- Implement auth in credentials file (`authenticate`, `test`, and properties).
- Add codex metadata in `<NodeName>.node.json`.
- Update `package.json`:
  - package name starts with `n8n-nodes-` (or scoped variant)
  - include `n8n-community-node-package` keyword
  - register node and credential JS paths under `n8n` field
  - include `"n8nNodesApiVersion": 1` inside the `n8n` object

## Companion References

- File structure: `references/06-node-file-structure.md`
- Credentials: `references/08-credentials.md`
- Codex metadata: `references/09-codex.md`
- UI elements: `references/07-ui-elements.md`
