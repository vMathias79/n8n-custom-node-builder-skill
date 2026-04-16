# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.2] - 2026-04-16

### Changed

- `references/07-ui-elements.md`: Added `htmlEditor` string field type via `typeOptions.editor`.
- `references/10-testing.md`: Renamed lint command to `npm run lint:fix`; switched linter config to `@n8n/node-cli` (`eslint.config.mjs`); added `~/.n8n/custom/` bootstrap (`mkdir custom && npm init`) and `N8N_CUSTOM_EXTENSIONS` guidance; expanded icon troubleshooting (square SVG canvas, 60×60 PNG).
- `references/11-community-deploy.md`: Added "Publishing to npm" section required for Creator Portal verification from May 1st 2026 — `npm create @n8n/node` scaffold, `npm run release` trigger, `@n8n/node-cli` >= 0.23.0 devDependency, npmjs.com Trusted Publishers (GitHub Actions) setup with `NPM_TOKEN` fallback; noted paid/enterprise competition rejection clause.
- `references/12-verification-guidelines.md`: Added one-third-party-service-per-package constraint (trigger for the same service allowed; proxies/multi-service packages rejected); added Package Source Verification section (npm repo URL must match GitHub, author consistency, public git link, MIT, GitHub Actions publish with provenance).
- Refreshed 4 reference snapshots per 45-day freshness policy; unchanged files (`01`–`06`, `08`, `09`, `13`) left untouched.

### Removed

- `references/CLAUDE.md`: Empty claude-mem context artifact.

## [1.0.1] - 2026-02-24

### Added

- `SKILL.md`: Build Lifecycle ASCII flow diagram showing the full node build pipeline.
- `SKILL.md`: Quick Reference table for instant routing to the correct reference file.
- `SKILL.md`: Start Here section with six contextual entry paths by task type.
- `tests/README.md`: RED-GREEN testing methodology and scenario index.
- `tests/scenarios/01-new-declarative-node.md`: Test scenario — build a declarative node end-to-end.
- `tests/scenarios/02-declarative-vs-programmatic.md`: Test scenario — style decision for multiple use cases.
- `tests/scenarios/03-credentials-implementation.md`: Test scenario — API key and Basic Auth credential implementation.
- `tests/scenarios/04-verification-prep.md`: Test scenario — pre-submission checklist for n8n community verification.
- `tests/scenarios/05-private-docker-install.md`: Test scenario — private Docker-based node installation.
- `CHANGELOG.md`: Version history in Keep a Changelog format.

### Changed

- Skill renamed from "n8n Node Builder" to "n8n Custom Node Builder Skill" across all files.
- Removed all Claude Code references; skill is now platform-agnostic and compatible with any agent that supports skills.
- `README.md`: Improved for GitHub public project — added badges, prerequisites, multiple usage examples, Contributing and Changelog sections; added `npx skills add` install command for skills.sh.
- `SKILL.md`: Updated author username to `vMathias79` throughout.
- `.gitignore`: Expanded to cover macOS, Windows, editors (VS Code, JetBrains, Vim), and environment files.
- `references/04-declarative.md`: Added `usableAsTool: true` property, `NodeConnectionTypes` import note, and icon guidelines (SVG preferred; PNG must be 60×60px).
- `references/05-programmatic.md`: Added `usableAsTool: true`; documented `IHttpRequestOptions`, `httpRequestWithAuthentication`, `constructExecutionMetaData`, and `continueOnFail()` patterns.
- `references/06-node-file-structure.md`: Added `n8n-node` CLI scaffolding recommendation; clarified `actions/` sub-structure (`<resourceName>.resource.ts` + `<operationName>.operation.ts` exports).
- `references/07-ui-elements.md`: Added `color` and `dateTime` field types; documented `typeOptions` variants for `string` and `number`.
- `references/09-codex.md`: Expanded category list to include Analytics, Finance & Accounting, Marketing & Content, Productivity, and Sales.
- `references/11-community-deploy.md`: Added upcoming requirement — from May 1st 2026, all community nodes must be published via a GitHub Action and include an npm provenance statement.
- `references/12-verification-guidelines.md`: Added provenance/GitHub Action requirement; added node type constraints (no duplicates of existing nodes; Logic and Flow control nodes not accepted).
- `references/README.md`: Updated retrieval timestamp to 2026-02-24.

## [1.0.0] - 2026-02-06

### Added

- `SKILL.md`: Skill definition with 10-step workflow router covering kickoff, planning, approach selection, build, file structure, UI parameters, credentials, codex, testing, and deployment.
- `references/README.md`: Reference index with source URL map and 45-day freshness policy.
- `references/01-overview.md`: Creating nodes lifecycle and prerequisites.
- `references/02-planning.md`: Pre-implementation design decisions and planning checklist.
- `references/03-approach-selection.md`: Decision rules for declarative vs programmatic style.
- `references/04-declarative.md`: Declarative build flow, required files, and packaging details.
- `references/05-programmatic.md`: Programmatic build flow including execute-path behavior.
- `references/06-node-file-structure.md`: Required files, directories, and modular layout.
- `references/07-ui-elements.md`: Parameter schema patterns and UI component selection.
- `references/08-credentials.md`: Credential file schema, auth injection, and credential testing.
- `references/09-codex.md`: Node metadata JSON requirements and synchronization rules.
- `references/10-testing.md`: Manual local testing, lint checks, and troubleshooting.
- `references/11-community-deploy.md`: Publishing and submission requirements for community node packages.
- `references/12-verification-guidelines.md`: Technical and policy constraints for verified community nodes.
- `references/13-private-install.md`: Installing custom nodes without publishing to npm.
- `agents/openai.yaml`: OpenAI-compatible agent interface definition.
- `AGENTS.md`: Contributor instructions.
- `README.md`: Project overview, installation, and structure documentation.

[Unreleased]: https://github.com/vMathias79/n8n-custom-node-builder-skill/compare/v1.0.2...HEAD
[1.0.2]: https://github.com/vMathias79/n8n-custom-node-builder-skill/compare/v1.0.1...v1.0.2
[1.0.1]: https://github.com/vMathias79/n8n-custom-node-builder-skill/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/vMathias79/n8n-custom-node-builder-skill/releases/tag/v1.0.0
