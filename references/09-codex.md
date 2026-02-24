# Node Codex File (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/build/reference/node-codex-files/
- Retrieved At (UTC): 2026-02-24T09:30:52Z
- Scope: Node metadata JSON requirements and synchronization rules.

## Purpose

Codex JSON stores node metadata used by n8n UI/help systems.

## Naming Rule

Codex filename must match base node filename:

- base: `MyNode.node.ts`
- codex: `MyNode.node.json`

## Required Metadata Concepts

- `node`: must start with `n8n-nodes-base.`
- `nodeVersion`: must match version in base node file
- `codexVersion`: docs currently reference `1.0`
- `categories`: choose from supported category names exactly
- `resources`: include helpful documentation links

## Category Naming

Use exact category strings (case and punctuation sensitive):

- Analytics
- Communication
- Data & Storage
- Development
- Finance & Accounting
- Marketing & Content
- Miscellaneous
- Productivity
- Sales
- Utility

Avoid near-miss variants (for example changing case or punctuation).
