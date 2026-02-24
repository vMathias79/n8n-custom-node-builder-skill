# Build Programmatic-Style Node (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/programmatic-style-node/
- Retrieved At (UTC): 2026-02-24T09:30:52Z
- Scope: Practical programmatic build flow including execute-path behavior.

## Prerequisites

- git
- Node.js + npm (Node 18.17.0 minimum in docs snippets)
- JavaScript/TypeScript
- REST APIs
- n8n expressions understanding

## Setup Flow

1. Start from n8n node starter or equivalent generated scaffold.
2. Remove template example files.
3. Create required node and credential files.
4. Install dependencies (`npm i`).

## Implementation Focus

- Import `NodeConnectionTypes` from `n8n-workflow` for `inputs`/`outputs`; import `IHttpRequestOptions` for request typing.
- Define resource + operation parameters in description.
- Set `usableAsTool: true` in description to allow AI agent tool use.
- Implement `execute()` for request assembly and response handling.
- Use `this.helpers.httpRequestWithAuthentication.call(this, 'credentialName', options)` for authenticated requests (preferred over `httpRequest`).
- Use `this.helpers.constructExecutionMetaData(returnJsonArray(data), { itemData: { item: i } })` to build output with proper item linking.
- Handle `continueOnFail()` inside the item loop for graceful per-item error handling.
- Read node parameters with defaults and use credential values from `getCredentials()`.
- Build explicit branching per resource/operation.
- Keep optional fields in collections.

## Authentication + Metadata + Packaging

- Configure credentials file with auth injection.
- Add codex JSON metadata file and keep it aligned with node version.
- Update `package.json` with naming, keywords, and `n8n` links to built artifacts.

## Companion References

- Approach decision rules: `references/03-approach-selection.md`
- File structure: `references/06-node-file-structure.md`
- Credentials: `references/08-credentials.md`
- Codex metadata: `references/09-codex.md`
