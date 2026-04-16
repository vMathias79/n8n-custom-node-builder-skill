# Community Verification Guidelines (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/reference/verification-guidelines/
- Retrieved At (UTC): 2026-04-16T08:48:00Z
- Scope: Technical and policy constraints for verified community nodes.

## High-Impact Requirements

- Use the `n8n-node` CLI tool for scaffolding, metadata, linting, and local load testing (required in practice for verified nodes).
- Ensure npm metadata and repository metadata are consistent and public.
- Package license must be MIT.
- Keep package documentation complete (README, usage examples, auth details).
- **From May 1st 2026**: All community nodes must be published via a GitHub Action and include an [npm provenance statement](https://docs.npmjs.com/generating-provenance-statements).

## Node Type Constraints

- The node **must not** duplicate an existing n8n node. If iterating on an existing node, open a pull request to the n8n repo instead.
- n8n is **not** currently accepting Logic or Flow control nodes.
- Each package must integrate **exactly one** third-party service. A trigger node for the same service may be included alongside the main node.
- Packages wrapping multiple unrelated APIs or acting as a proxy layer for several services generally don't qualify — submit each service as its own separate package.

## Package Source Verification

- The npm package repository URL must match the expected GitHub repository.
- The package author / maintainer must match between npm and the repository.
- The git link on npm must work and the repository must be public.
- Package license must be MIT.
- Packages must be published from a GitHub Action and include provenance.

## Security and Runtime Constraints

- No external runtime dependencies (keep the package lightweight).
- No filesystem access in node runtime logic.
- No environment variable access in node runtime logic.
- Pass all operational values through node parameters and credentials.

## Quality Constraints

- Use TypeScript; follow n8n's node development guidelines.
- Consistent coding style, proper error handling and validation.
- Ensure lint/scanner checks pass:
  ```shell
  npx @n8n/scan-community-package n8n-nodes-PACKAGE
  ```
- Node interface and all documentation must be in English only (parameter names, descriptions, help text, error messages, README).

## Verification Checklist

- [ ] Single third-party service per package (trigger for same service allowed)
- [ ] Repository URL and npm metadata align; public repo; maintainer matches
- [ ] MIT license
- [ ] Published via GitHub Actions with npm provenance
- [ ] No runtime dependencies, filesystem, or env var access
- [ ] Scanner (`npx @n8n/scan-community-package`) passes
- [ ] English-only UI/docs
