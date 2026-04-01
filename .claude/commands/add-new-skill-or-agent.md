---
name: add-new-skill-or-agent
description: Workflow command scaffold for add-new-skill-or-agent in everything-claude-code.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-new-skill-or-agent

Use this workflow when working on **add-new-skill-or-agent** in `everything-claude-code`.

## Goal

Adds a new skill or agent to the system, including documentation and registration in manifests.

## Common Files

- `skills/*/SKILL.md`
- `.claude/skills/*/SKILL.md`
- `.agents/skills/*/SKILL.md`
- `agents/*.md`
- `manifests/install-modules.json`
- `README.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create SKILL.md in skills/<skill-name>/ or .claude/skills/<skill-name>/ or .agents/skills/<skill-name>/.
- Create agent definition(s) in agents/<agent-name>.md if needed.
- Update manifests/install-modules.json or other relevant manifest files.
- Add or update documentation (README.md, AGENTS.md, etc.).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.