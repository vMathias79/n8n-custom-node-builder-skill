# Test a Node (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/test/
- Retrieved At (UTC): 2026-02-06T18:01:47Z
- Scope: Manual local testing, lint checks, and common troubleshooting.

## Required Testing Modes

Use both:

1. Manual local execution in n8n.
2. Automated/static lint checks.

## Local Run Workflow

1. Install n8n globally:
   ```shell
   npm install n8n -g
   ```
2. Build and link your node package from its root:
   ```shell
   npm run build
   npm link
   ```
3. Link package inside n8n custom extensions directory:
   ```shell
   npm link <node-package-name>
   ```
4. Start n8n:
   ```shell
   n8n start
   ```
5. Verify node appears in the node picker by node name.

## Lint Workflow

```shell
npm run lint
npm run lintfix
```

Linter source: `eslint-plugin-n8n-nodes-base`.

## Troubleshooting Highlights

- Unknown credentials type: confirm credential class/property names and references match.
- Node not visible: verify package registration under `package.json` `n8n` field.
- Icon issues: check path, format (`.svg`/`.png`), and `file:` prefix.
- UI description changes not visible: restart local n8n process and re-link if needed.
- File-case lint issues on Windows: account for OS rename edge case.

## Primary Related URLs

- https://docs.n8n.io/integrations/creating-nodes/test/run-node-locally/
- https://docs.n8n.io/integrations/creating-nodes/test/node-linter/
- https://docs.n8n.io/integrations/creating-nodes/test/troubleshooting-node-development/
