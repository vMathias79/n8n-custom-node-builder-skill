# Scenario 4: Prepare Node for n8n Community Verification

## Prompt

```
You are an AI coding assistant. A developer asks you:

"I've built an n8n community node and I want to get it verified by n8n
so it appears in the verified nodes panel. What do I need to check and do
before submitting it? Give me a complete pre-submission checklist."
```

## Expected Correctness Criteria

### Tooling (12-verification-guidelines.md)
- [ ] Recommends using the `n8n-node` CLI tool for scaffolding and checks
- [ ] Mentions running the scanner: `npx @n8n/scan-community-package n8n-nodes-PACKAGE`
- [ ] States scanner must pass before submission

### Node type constraints (12-verification-guidelines.md)
- [ ] States node must NOT duplicate an existing built-in n8n node (create a PR instead)
- [ ] States Logic or Flow control nodes are not currently accepted

### Security and runtime constraints (12-verification-guidelines.md)
- [ ] No external runtime dependencies allowed
- [ ] No filesystem access in node runtime code
- [ ] No environment variable access in node runtime code
- [ ] All necessary data must pass through node parameters and credentials

### Package and metadata requirements (12-verification-guidelines.md, 11-community-deploy.md)
- [ ] Package license must be MIT
- [ ] npm package name starts with `n8n-nodes-`
- [ ] npm metadata and GitHub repository metadata must match
- [ ] Repository must be public
- [ ] README must include usage instructions and documentation

### Publishing requirement (12-verification-guidelines.md, 11-community-deploy.md)
- [ ] From May 1st 2026: all community nodes must be published via a GitHub Action
- [ ] Must include an npm provenance statement

### Language requirement (12-verification-guidelines.md)
- [ ] Node UI, parameter names, descriptions, error messages, and README must all be in English only

### Submission (11-community-deploy.md)
- [ ] Submit via n8n Creator Portal: https://creators.n8n.io/nodes
- [ ] npm package must be published and available before submission
