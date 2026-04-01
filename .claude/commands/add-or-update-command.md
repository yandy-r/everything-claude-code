---
name: add-or-update-command
description: Workflow command scaffold for add-or-update-command in everything-claude-code.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-command

Use this workflow when working on **add-or-update-command** in `everything-claude-code`.

## Goal

Adds or updates a command markdown file, defining new CLI commands or workflows.

## Common Files

- `commands/*.md`
- `.claude/commands/*.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or update a markdown file in the commands/ or .claude/commands/ directory.
- Document the command's usage, arguments, and output.
- Optionally update related documentation or index files.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.