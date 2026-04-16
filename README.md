# n8n Custom Node Builder Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![References updated](https://img.shields.io/badge/references%20updated-2026--04--16-blue)](#reference-docs)

> An agentic skill that guides you through the full lifecycle of building n8n custom nodes — from planning through deployment. Compatible with any AI agent that supports skills.

## What It Does

This skill provides a structured, reference-first workflow for creating n8n community or private nodes:

1. **Plan** — define node scope, auth model, error handling, and deployment target
2. **Choose style** — declarative (default) vs programmatic, with explicit justification
3. **Build** — implement resources, operations, credentials, and codex metadata
4. **Validate** — check file structure, UI parameters, and package configuration
5. **Test** — run manual local tests and lint checks
6. **Deploy** — publish as a community package or install privately

All guidance is backed by local reference snapshots of the official n8n documentation, so the skill works reliably offline.

## Prerequisites

- An AI agent with skill/plugin support (e.g. OpenAI Assistants, or any compatible agent platform)
- Node.js ≥ 18.17.0 and npm (for building and testing nodes)
- Familiarity with n8n, TypeScript, and REST APIs

## Installation

```bash
npx skills add vMathias79/n8n-custom-node-builder-skill
```

Or clone manually into your agent's skills directory:

```bash
git clone https://github.com/vMathias79/n8n-custom-node-builder-skill.git path/to/your/skills/n8n-custom-node-builder-skill
```

## Usage

Invoke the skill in your agent session:

```
Use n8n-custom-node-builder-skill to build a declarative node for the GitHub API
```

```
Use n8n-custom-node-builder-skill to add OAuth2 credentials to my existing node
```

```
Use n8n-custom-node-builder-skill to prepare my node package for n8n community verification
```

## Project Structure

```
n8n-custom-node-builder-skill/
├── SKILL.md              # Skill definition and workflow router (entry point)
├── AGENTS.md             # Contributor guidelines
├── CHANGELOG.md          # Version history
├── LICENSE               # MIT
├── README.md
├── agents/
│   └── openai.yaml       # OpenAI-compatible agent interface
├── tests/
│   ├── README.md         # RED-GREEN testing methodology
│   └── scenarios/        # 5 test scenarios with correctness criteria
├── references/           # Curated n8n docs snapshots (13 files)
│   ├── README.md         # Reference index with source URLs and freshness policy
│   ├── 01-overview.md    # Creating nodes overview
│   ├── 02-planning.md    # Planning your node
│   ├── 03-approach-selection.md
│   ├── 04-declarative.md
│   ├── 05-programmatic.md
│   ├── 06-node-file-structure.md
│   ├── 07-ui-elements.md
│   ├── 08-credentials.md
│   ├── 09-codex.md
│   ├── 10-testing.md
│   ├── 11-community-deploy.md
│   ├── 12-verification-guidelines.md
│   └── 13-private-install.md
```

The `agents/` directory contains interface definitions for specific agent platforms. Currently includes an OpenAI-compatible configuration (`openai.yaml`).

## Reference Docs

The `references/` directory contains curated snapshots of the [n8n creating-nodes documentation](https://docs.n8n.io/integrations/creating-nodes/). These are summarized and reorganized for efficient AI consumption — not verbatim copies.

Each reference file includes its source URL and retrieval timestamp. References follow a **45-day freshness policy** — see [`references/README.md`](references/README.md) for the full source URL map and update instructions.

### Attribution

The reference material is derived from the [n8n documentation](https://github.com/n8n-io/n8n-docs), which is licensed under the [Sustainable Use License](https://docs.n8n.io/sustainable-use-license/) (Apache 2.0 + Commons Clause). All source URLs are preserved in each reference file and in `references/README.md`.

## Contributing

See [AGENTS.md](AGENTS.md) for guidelines on updating reference files and contributing to the skill definition.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for the full version history.

## License

This skill is licensed under the [MIT License](LICENSE).

The reference documentation in `references/` is derived from n8n's official documentation, which is subject to its own [license terms](https://github.com/n8n-io/n8n-docs/blob/main/LICENSE.md).
