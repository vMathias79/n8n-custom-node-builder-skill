---
name: n8n-custom-node-builder-skill
description: Plan, build, test, verify, and deploy n8n custom nodes and credentials for community packages or private installs. Use when creating new nodes, extending existing nodes, choosing declarative vs programmatic style, implementing credential auth, designing node UI parameters, enforcing n8n verification constraints, and preparing release or private deployment.
---

# n8n Custom Node Builder Skill

## Goal

Implement or extend n8n nodes end-to-end using a reference-first workflow that is stable offline.

## Reference-First Rule

Before each lifecycle step, load the matching local file from `references/`.

- Start every task with `references/README.md` and `references/01-overview.md`.
- Do not browse external docs unless local references are stale or missing a required detail.
- If any reference is stale (older than 45 days), refresh only the changed files and update timestamps.

## Workflow Router

### 0) Kickoff and context

Load:

- `references/README.md`
- `references/01-overview.md`

Do:

- Confirm task scope (new node, extension, verification prep, or private install).
- Confirm intended deployment target (community vs private).

### 1) Plan node scope

Load:

- `references/02-planning.md`

Do:

- Define node type and target API resources/operations.
- Define auth model and required permissions/scopes.
- Define error handling and retry/timeouts.
- Define expected outputs and data mapping behavior.

### 2) Choose implementation style

Load:

- `references/03-approach-selection.md`

Do:

- Default to declarative style.
- Use programmatic style when trigger behavior, non-REST behavior, custom transforms, or full versioning requires it.
- Record style choice in implementation notes before coding.

### 3) Build the node (style-specific)

Load one:

- `references/04-declarative.md`
- `references/05-programmatic.md`

Do:

- Implement resource/operation structure.
- Keep operation lists and parameter naming consistent.
- Keep optional inputs behind collections.

### 4) Validate file structure

Load:

- `references/06-node-file-structure.md`

Do:

- Ensure required package, node, and credential files exist.
- Apply modular structure (`actions`, `methods`, `transport`) for non-trivial nodes.
- Confirm multi-node package layout when relevant.

### 5) Implement UI parameters

Load:

- `references/07-ui-elements.md`

Do:

- Use suitable field types and `displayOptions` gates.
- Use `resourceLocator` and `resourceMapper` where they improve UX.
- Keep labels/descriptions concise and in English.

### 6) Implement credentials

Load:

- `references/08-credentials.md`

Do:

- Define credential properties and auth injection.
- Add a credential test request.
- Keep secret handling and property naming consistent.

### 7) Maintain codex metadata

Load:

- `references/09-codex.md`

Do:

- Keep codex filename aligned with base node filename.
- Keep `nodeVersion` aligned with base file version.
- Keep categories and docs resources valid.

### 8) Test and troubleshoot

Load:

- `references/10-testing.md`

Do:

- Run manual local tests.
- Run lint checks (`npm run lint`, `npm run lintfix`).
- Address common issues (missing registration, credential mismatch, icon path/type, stale local process).

### 9) Deploy

#### Community package path

Load:

- `references/11-community-deploy.md`
- `references/12-verification-guidelines.md`

Do:

- Ensure package standards are met.
- Run scanner checks:
  ```shell
  npx @n8n/scan-community-package n8n-nodes-PACKAGE
  ```
- Publish to npm and submit via Creator Portal if verification is required.

#### Private installation path

Load:

- `references/13-private-install.md`

Do:

- Build package artifacts.
- Install into target runtime (Docker or global environment).
- Restart n8n and validate node visibility + execution.

### 10) Update package documentation and tracking

Load:

- `references/11-community-deploy.md` (for publish requirements)
- `references/12-verification-guidelines.md` (if verification target)

Do:

- Update README and usage examples.
- Update API coverage/status tracking.
- Record verification-related constraints and outcomes.

## Non-Negotiable Constraints

- Keep node interface and docs text in English.
- Avoid environment variable and filesystem access in node runtime logic for verification targets.
- Keep package metadata, repository links, and maintainer details consistent.
- Prefer n8n-node generated/scaffolded structure for verified community submissions.

## Completion Checklist

- [ ] Planning decisions documented
- [ ] Declarative/programmatic choice explicitly justified
- [ ] Required file structure present
- [ ] Credentials file and credential tests implemented
- [ ] Codex metadata aligned with node base file
- [ ] Manual local testing completed
- [ ] Lint/scanner checks completed as required
- [ ] Deployment path executed and validated
- [ ] README/tracking updates completed
