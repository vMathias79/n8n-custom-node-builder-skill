# Contributing to n8n Custom Node Builder Skill

This is an agentic skill. The main skill definition lives in `SKILL.md`.

## Project Structure

- `SKILL.md` — Skill definition (frontmatter + workflow)
- `references/` — Curated snapshots of n8n creating-nodes documentation
- `agents/` — Alternative agent interface definitions (e.g. OpenAI)
- `tests/` — RED-GREEN test scenarios for skill validation

## Updating References

References have a 45-day freshness policy. To refresh:

1. Check source URLs listed in `references/README.md`
2. Update only files whose source pages changed
3. Update the `Retrieved At (UTC)` timestamp in changed files
4. Keep unchanged files untouched