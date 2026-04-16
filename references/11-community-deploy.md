# Submit Community Nodes (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/deploy/submit-community-nodes/
- Retrieved At (UTC): 2026-04-16T08:48:00Z
- Scope: Publishing and submission requirements for community node packages.

## Core Standards

- Package name starts with `n8n-nodes-` (or scoped `@<scope>/n8n-nodes-...`).
- Include `n8n-community-node-package` in keywords.
- Register nodes and credentials in `package.json` under `n8n`.
- Run local quality checks before publish (`npm run lint`, `npm run dev`).
- Publish the package to npm. Use the `n8n-node` CLI tool during development — strongly recommended and effectively required for verified nodes.

## Publishing to npm

**Required for Creator Portal verification.** From May 1st 2026, nodes submitted for verification must be published via a GitHub Actions workflow with an [npm provenance statement](https://docs.npmjs.com/generating-provenance-statements). n8n will not accept verified nodes published directly from a local machine. Provenance lets anyone cryptographically verify the workflow, repository, and commit that produced the package (signed by GitHub Actions' OIDC infrastructure).

### New Nodes

Scaffold with `npm create @n8n/node`. The scaffold includes a ready-to-use `publish.yml` workflow. Run `npm run release` locally to bump the version, commit, tag, and push — this triggers the workflow to publish to npm.

### Existing Nodes

- Add the publish workflow from `n8n-nodes-starter` at `.github/workflows/publish.yml`.
- Ensure `@n8n/node-cli` is a `devDependency` at version `0.23.0` or later (earlier versions lack the provenance flag used by the workflow). Verify with `npm list @n8n/node-cli`.

### One-Time npm Trusted Publisher Setup

Preferred (no long-lived token):

1. Log in to npmjs.com and open the package's settings.
2. Under **Publish access > Trusted Publishers**, click **Add a publisher**.
3. Select **GitHub Actions** and fill in:
   - Repository owner: your GitHub user/org
   - Repository name: your repository name
   - Workflow name: `publish.yml` (the filename)

Token fallback: create a Granular Access Token on npmjs.com and store it as `NPM_TOKEN` in the repository's Actions secrets.

## Verification Submission Requirements

Before Creator Portal submission:

- Start from the `n8n-node` CLI scaffolding (strongly recommended — required in practice for verified nodes).
- Follow the technical verification guidelines (no runtime dependencies, etc.).
- Follow the UX guidelines.
- Provide clear public documentation (README in the npm package or a related public repo).
- Publish to npm via GitHub Actions with provenance (see above).
- Note: n8n may reject nodes that compete with its paid/enterprise features.

## Submission Path

Use n8n Creator Portal:

- https://creators.n8n.io/nodes

## Related References

- `references/12-verification-guidelines.md`
- https://docs.n8n.io/integrations/creating-nodes/build/reference/ux-guidelines/
