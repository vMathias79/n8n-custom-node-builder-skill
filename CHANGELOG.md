# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.1] - 2026-02-24

### Changed

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

[Unreleased]: https://github.com/YOUR_USERNAME/n8n-custom-node-builder-skill/compare/v1.0.1...HEAD
[1.0.1]: https://github.com/YOUR_USERNAME/n8n-custom-node-builder-skill/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/YOUR_USERNAME/n8n-custom-node-builder-skill/releases/tag/v1.0.0
