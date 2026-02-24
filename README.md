# n8n Custom Node Builder Skill

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that guides you through the full lifecycle of building n8n custom nodes — from planning through deployment.

## What It Does

This skill provides a structured, reference-first workflow for creating n8n community or private nodes. It walks you through:

1. Planning node scope, auth model, and error handling
2. Choosing declarative vs programmatic implementation style
3. Building the node with consistent patterns
4. Validating file structure, UI parameters, credentials, and codex metadata
5. Testing and linting
6. Deploying as a community package or private installation

All guidance is backed by local reference snapshots of the official n8n documentation, so the skill works reliably offline.

## Installation

Clone this repository into your Claude Code skills directory:

```bash
git clone https://github.com/YOUR_USERNAME/n8n-custom-node-builder-skill.git ~/.claude/skills/n8n-custom-node-builder-skill
```

Then reference the skill in your Claude Code session:

```
Use n8n-custom-node-builder-skill to create a custom node for the Acme API
```

## Project Structure

```
n8n-custom-node-builder-skill/
├── SKILL.md              # Skill definition (entry point)
├── references/           # Curated n8n docs snapshots (13 files)
│   ├── README.md         # Reference index with source URLs
│   ├── 01-overview.md    # Creating nodes overview
│   ├── 02-planning.md    # Planning your node
│   ├── ...
│   └── 13-private-install.md
├── agents/
│   └── openai.yaml       # OpenAI-compatible agent interface
├── CLAUDE.md             # Contributor instructions
├── LICENSE               # MIT
└── README.md
```

### `agents/` Directory

The `agents/` directory contains alternative interface definitions for using this skill outside Claude Code. Currently includes an OpenAI-compatible agent configuration (`openai.yaml`).

## Reference Docs

The `references/` directory contains curated snapshots of the [n8n creating-nodes documentation](https://docs.n8n.io/integrations/creating-nodes/). These are summarized and reorganized for efficient AI consumption, not verbatim copies.

Each reference file includes its source URL and retrieval timestamp. References follow a 45-day freshness policy — see `references/README.md` for the full source URL map.

### Attribution

The reference material is derived from the [n8n documentation](https://github.com/n8n-io/n8n-docs), which is licensed under the [Sustainable Use License](https://docs.n8n.io/sustainable-use-license/) (Apache 2.0 + Commons Clause). All source URLs are preserved in each reference file and in `references/README.md`.

## License

This skill is licensed under the [MIT License](LICENSE).

The reference documentation in `references/` is derived from n8n's official documentation, which is subject to its own [license terms](https://github.com/n8n-io/n8n-docs/blob/main/LICENSE.md).
