```markdown
# everything-claude-code Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill introduces the core development patterns, coding conventions, and common workflows for contributing to the `everything-claude-code` repository. The project is JavaScript-based, with no framework dependencies, and emphasizes modularity, agentic skills, and workflow automation. This guide covers file organization, commit conventions, code style, workflow steps, and testing patterns to help you contribute effectively and consistently.

## Coding Conventions

- **File Naming:** Use camelCase for JavaScript files and folders.
  - Example: `mySkill.js`, `installTarget.js`
- **Import Style:** Use relative imports.
  - Example:
    ```js
    const helper = require('./utils/helper');
    ```
- **Export Style:** Mixed (both CommonJS and ES module styles may be present).
  - Example (CommonJS):
    ```js
    module.exports = function mySkill() { ... };
    ```
  - Example (ESM):
    ```js
    export default function mySkill() { ... }
    ```
- **Commit Messages:** Follow [Conventional Commits](https://www.conventionalcommits.org/) with prefixes such as `fix`, `feat`, `docs`, `chore`.
  - Example: `feat: add support for new install target`
- **Test Files:** Use the pattern `*.test.js` for test files.

## Workflows

### Add or Update a Skill
**Trigger:** When introducing or updating a workflow, agent, or capability  
**Command:** `/add-skill`

1. Create or update a `SKILL.md` file in one of:
    - `skills/<skill-name>/SKILL.md`
    - `.agents/skills/<skill-name>/SKILL.md`
    - `.claude/skills/<skill-name>/SKILL.md`
2. Optionally update `AGENTS.md`, `README.md`, or `manifests/install-modules.json` to reference the new skill.
3. Document the skill's usage and integration points.

**Example:**
```bash
/add-skill
```

---

### Add or Update a Command
**Trigger:** When adding a new CLI command, workflow, or extending command capabilities  
**Command:** `/add-command`

1. Create or update a markdown file in `commands/` (e.g., `commands/<command>.md`).
2. Optionally update related documentation (`README.md`, `AGENTS.md`).
3. If the command is part of a workflow, update or create associated artifacts or scripts.

**Example:**
```bash
/add-command
```

---

### Add or Update an Agent
**Trigger:** When introducing a new agent or updating agent logic  
**Command:** `/add-agent`

1. Create or update agent definition markdown in `agents/<agent-name>.md` or `.opencode/prompts/agents/<agent>.txt`.
2. Register or update the agent in `opencode.json` or related config.
3. Update `AGENTS.md` with new agent details.

**Example:**
```bash
/add-agent
```

---

### Add or Update an Install Target
**Trigger:** When supporting a new platform/tool for installation/integration  
**Command:** `/add-install-target`

1. Create or update install scripts (`.sh`/`.js`) and documentation in a dot-directory (e.g., `.codebuddy/`, `.gemini/`).
2. Update `manifests/install-modules.json` and `schemas/ecc-install-config.schema.json`.
3. Update `scripts/lib/install-manifests.js` and `scripts/lib/install-targets/<target>.js`.
4. Add or update tests for install targets.

**Example:**
```bash
/add-install-target
```

---

### Add or Update CI Workflow
**Trigger:** When updating CI workflows, adding new checks, or bumping dependencies  
**Command:** `/update-ci`

1. Edit or add files in `.github/workflows/`.
2. Update `package.json` or `yarn.lock` if dependency-related.
3. Test CI to ensure the new workflow or dependency works as intended.

**Example:**
```bash
/update-ci
```

---

### Update Hooks or Validation Scripts
**Trigger:** When improving or fixing pre/post hooks, or validation logic for edits and CI  
**Command:** `/update-hooks`

1. Edit `hooks/hooks.json` and supporting scripts in `scripts/hooks/`.
2. Update or add tests in `tests/hooks/` or `tests/scripts/`.
3. Optionally update related documentation.

**Example:**
```bash
/update-hooks
```

---

### Add or Update Documentation
**Trigger:** When documenting new workflows, updating guides, or adding troubleshooting info  
**Command:** `/update-docs`

1. Edit or add markdown files in `docs/`, `WORKING-CONTEXT.md`, or `the-shortform-guide.md`.
2. Update `README.md` and/or `README.zh-CN.md`.
3. Optionally update related skill or agent docs.

**Example:**
```bash
/update-docs
```

## Testing Patterns

- **Test Files:** Place tests in the same directory as the code or in a `tests/` directory, using the `*.test.js` naming convention.
- **Framework:** No specific testing framework detected; use standard JavaScript test runners (e.g., Jest, Mocha) as appropriate.
- **Example Test File:**
    ```js
    // mySkill.test.js
    const mySkill = require('./mySkill');

    test('should return expected result', () => {
      expect(mySkill('input')).toBe('expected output');
    });
    ```

## Commands

| Command             | Purpose                                                      |
|---------------------|--------------------------------------------------------------|
| /add-skill          | Add or update a skill (workflow, agent, or capability)       |
| /add-command        | Add or update a command file for new or extended workflows   |
| /add-agent          | Add or update an agent definition                            |
| /add-install-target | Add or update an install target for external integrations    |
| /update-ci          | Add or update CI/CD workflow files or dependencies           |
| /update-hooks       | Update hooks or validation scripts                           |
| /update-docs        | Add or update documentation                                  |
```
