# Skill Tests

Tests for the `n8n-custom-node-builder-skill` using the RED-GREEN methodology.

## Skill Type

This is a **workflow/reference** skill, so tests focus on:

- **Retrieval** — Does the agent load the right reference file(s) for a given task?
- **Application** — Does the agent produce correct, specific, actionable guidance?
- **Coverage** — Are common n8n node development scenarios adequately handled?

## Test Scenarios

| # | Scenario | Tests | Key Reference(s) |
|---|----------|-------|------------------|
| 1 | Build a new declarative node from scratch | Retrieval + Application | 04-declarative.md, 06-node-file-structure.md, 09-codex.md |
| 2 | Choose declarative vs programmatic style | Retrieval + Application | 03-approach-selection.md, 05-programmatic.md |
| 3 | Implement credentials and auth injection | Retrieval + Application | 08-credentials.md |
| 4 | Prepare node for n8n community verification | Retrieval + Application | 12-verification-guidelines.md, 11-community-deploy.md |
| 5 | Install a custom node privately in Docker | Retrieval + Application | 13-private-install.md |

## Running Tests

Each scenario in `scenarios/` is a self-contained prompt. Run with a subagent:

**RED (baseline):** Run the prompt as-is — no skill loaded. The agent uses only general knowledge.

**GREEN (with skill):** Prepend the following to the prompt before running:

```
You have access to an n8n custom node builder skill with references in <path>.
Read SKILL.md first, then load the relevant reference file(s) listed in the Quick Reference table.
```

Compare outputs against each scenario's **Expected Correctness Criteria** checkboxes.

A passing GREEN result should check significantly more boxes than the RED baseline — especially for n8n-specific details (exact field names, package.json keys, scanner commands, etc.) that are unlikely to appear in general training data.
