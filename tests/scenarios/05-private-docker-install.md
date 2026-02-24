# Scenario 5: Install Custom Node Privately in Docker

## Prompt

```
You are an AI coding assistant. A developer asks you:

"I've built a custom n8n node for internal use at my company.
I don't want to publish it to npm. We run n8n using Docker.
How do I install my custom node into our Docker-based n8n instance?"
```

## Expected Correctness Criteria

### Build step (13-private-install.md)
- [ ] Instructs developer to build the node package first: `npm run build`
- [ ] States built artifacts are in the `dist/` folder

### Dockerfile setup (13-private-install.md)
- [ ] Instructs creating a Dockerfile based on n8n's official Dockerfile
- [ ] References copying node and credential files into `~/.n8n/custom/` inside the container
- [ ] Mentions downloading `docker-entrypoint.sh` and placing it alongside the Dockerfile

### Build command (13-private-install.md)
- [ ] Provides the exact build command pattern:
  `docker build --build-arg N8N_VERSION=<n8n-version-number> --tag=customizedn8n .`
- [ ] Notes that `N8N_VERSION` must be replaced with the actual n8n release version

### Post-install validation (13-private-install.md)
- [ ] Instructs restarting n8n after installation
- [ ] Instructs verifying the node appears in the n8n node picker
- [ ] Mentions validating credential entry and operation execution in the UI

### Global install alternative (13-private-install.md)
- [ ] Mentions that if n8n is globally installed (non-Docker), install the node package in the same runtime environment so n8n loads it automatically
