# Install Private Nodes (Curated)

- Source URL: https://docs.n8n.io/integrations/creating-nodes/deploy/install-private-nodes/
- Retrieved At (UTC): 2026-02-06T18:01:47Z
- Scope: Installing custom nodes without publishing to npm public registry.

## Docker-Based n8n

1. Build node package (`npm run build`).
2. Copy built `dist/nodes` and `dist/credentials` content into `~/.n8n/custom/` inside the container image/runtime.
3. Build a custom n8n image using the documented n8n Dockerfile pattern.
4. Start container and verify node appears in node picker.

Build command pattern from docs:

```shell
docker build --build-arg N8N_VERSION=<n8n-version-number> --tag=customizedn8n .
```

## Global n8n Installation

If n8n is globally installed, install your node package in the same runtime environment so n8n can load it automatically.

## Operational Notes

- Keep build artifacts current before copying/installing.
- Restart n8n after installation changes.
- Validate credentials and operation execution in UI after install.
