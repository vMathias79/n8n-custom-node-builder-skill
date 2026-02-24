# Community Verification Guidelines (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/reference/verification-guidelines/
- Retrieved At (UTC): 2026-02-24T09:30:52Z
- Scope: Technical and policy constraints for verified community nodes.

## High-Impact Requirements

- Use `n8n-node` CLI tool for scaffolding and checks (required for verified nodes).
- Ensure npm metadata and repository metadata are consistent and public.
- Package license should be MIT.
- Keep package documentation complete.
- **From May 1st 2026**: All community nodes must be published via a GitHub Action and include an [npm provenance statement](https://docs.npmjs.com/generating-provenance-statements).

## Node Type Constraints

- Your node **must not** duplicate an existing built-in n8n node. If extending an existing node, open a pull request to the n8n repo instead.
- n8n is **not** currently accepting Logic or Flow control nodes.

## Security and Runtime Constraints

- No runtime external dependencies for verified nodes.
- No filesystem access in node runtime logic.
- No environment variable access in node runtime logic.
- Pass operational values through node parameters and credentials.

## Quality Constraints

- Follow n8n code and UX best practices.
- Ensure lint/scanner checks pass:
  ```shell
  npx @n8n/scan-community-package n8n-nodes-PACKAGE
  ```
- Keep node interface and documentation in English.

## Verification Checklist

- [ ] Repository URL and npm metadata align
- [ ] Public repo and maintainer metadata are correct
- [ ] No forbidden runtime behavior/dependencies
- [ ] Scanner passes
- [ ] English-only UI/docs
