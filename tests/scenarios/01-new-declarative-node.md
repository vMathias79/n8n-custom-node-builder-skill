# Scenario 1: Build a New Declarative Node from Scratch

## Prompt

```
You are an AI coding assistant. A developer asks you:

"I want to build a custom n8n node for the OpenWeatherMap REST API.
It should support two resources: Current Weather and Forecast.
Each resource needs a Get operation.
How do I build this end-to-end as a declarative-style node?"

Provide a complete, step-by-step implementation guide including file structure,
key code patterns, package.json configuration, and how to test it locally.
```

## Expected Correctness Criteria

### Scaffolding (04-declarative.md, 06-node-file-structure.md)
- [ ] Recommends using `n8n-node` CLI tool OR n8n-nodes-starter repository
- [ ] Lists required files: `nodes/<NodeName>/<NodeName>.node.ts`, `nodes/<NodeName>/<NodeName>.node.json`, `credentials/<NodeName>Api.credentials.ts`
- [ ] Mentions `npm i` to install dependencies after setup

### Node description (04-declarative.md)
- [ ] Imports `NodeConnectionTypes` from `n8n-workflow`
- [ ] Sets `usableAsTool: true` in the description object
- [ ] Uses `requestDefaults.baseURL` for the API base URL
- [ ] Uses `icon: 'file:<icon>.svg'` and notes SVG is preferred (PNG must be 60×60px)

### Resources and operations (04-declarative.md)
- [ ] Defines a `resource` field of type `options` with `noDataExpression: true`
- [ ] Uses `routing.request` inside operation options to define HTTP method and URL
- [ ] Uses `displayOptions.show` to gate operation fields to their resource

### Optional fields (04-declarative.md, 07-ui-elements.md)
- [ ] Wraps optional parameters in a `collection` type field named `Additional Fields` or similar

### package.json (04-declarative.md)
- [ ] Package name starts with `n8n-nodes-`
- [ ] Includes `n8n-community-node-package` in `keywords`
- [ ] Registers built node and credential paths under the `n8n` field
- [ ] Includes `"n8nNodesApiVersion": 1` inside the `n8n` object

### Codex metadata (09-codex.md)
- [ ] `node` field starts with `n8n-nodes-base.`
- [ ] `nodeVersion` matches version in the base node file
- [ ] `codexVersion` is `"1.0"`
- [ ] `categories` uses a valid category string (e.g. `"Miscellaneous"`, `"Data & Storage"`)
- [ ] Codex filename matches base node filename (e.g. `MyNode.node.json` for `MyNode.node.ts`)

### Local testing (10-testing.md)
- [ ] Mentions `npm run build` + `npm link` to publish locally
- [ ] Mentions linking package inside n8n: `npm link <package-name>`
- [ ] Mentions starting n8n with `n8n start`
- [ ] Mentions `npm run lint` for lint checks
