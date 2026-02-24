# Plan a Node (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/plan/
- Retrieved At (UTC): 2026-02-06T18:01:47Z
- Scope: Pre-implementation design decisions and planning checklist.

## Purpose

Use this reference to define implementation intent before writing code.

## Required Planning Decisions

1. Node type to build (action/app/trigger/etc.).
2. Node-building style choice (declarative or programmatic).
3. UI/UX design constraints for parameters and operations.
4. File structure and packaging strategy.

## Planning Outputs

Produce these artifacts before implementation:

- Resource-operation matrix.
- Auth model and credential requirements.
- Input/output schemas and pagination model.
- Error-handling behavior (including `continueOnFail()` expectations).
- Test strategy (manual local + lint/static checks).
- Deployment target (community verified, community non-verified, or private).

## Related Pages

- Node type guidance: https://docs.n8n.io/integrations/creating-nodes/plan/node-types/
- Node UI design: https://docs.n8n.io/integrations/creating-nodes/plan/node-ui-design/
- Build approach selection: `references/03-approach-selection.md`
- File structure reference: `references/06-node-file-structure.md`
