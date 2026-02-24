# Choose Node Building Approach (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/plan/choose-node-method/
- Retrieved At (UTC): 2026-02-06T18:01:47Z
- Scope: Decision rules for declarative vs programmatic implementation.

## Default Rule

Use declarative style for most nodes.

Why:

- JSON-based syntax is simpler and less error-prone.
- Better long-term maintainability and future compatibility.
- Strong fit for REST API integrations.

## Use Programmatic Style When

- Building a trigger node.
- Integrating with non-REST APIs (including GraphQL scenarios).
- Needing custom transformation of incoming data.
- Implementing full versioning or advanced execution logic.

## Data Handling Difference

- Programmatic style builds requests in `execute()` and reads incoming items/params explicitly.
- Declarative style defines request and mapping behavior through `routing` in operation descriptions.

## Decision Checklist

- Is this integration REST-only and non-trigger? Prefer declarative.
- Do you need custom runtime logic beyond routing? Use programmatic.
- Do you need full versioning behaviors? Use programmatic.

## Companion References

- Declarative implementation: `references/04-declarative.md`
- Programmatic implementation: `references/05-programmatic.md`
