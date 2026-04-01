```markdown
# everything-claude-code Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches the core development patterns, coding conventions, and common workflows used in the `everything-claude-code` repository. The codebase is primarily JavaScript, with no major framework, and is organized around modular skills, agent definitions, command workflows, and extensible install targets. The repository emphasizes clear documentation, conventional commits, and maintainable architecture for agent and workflow development.

## Coding Conventions

- **File Naming:**  
  Use `camelCase` for JavaScript files and directories.  
  *Example:*  
  ```
  scripts/lib/installTargets.js
  agentPrompts.md
  ```

- **Import Style:**  
  Use **relative imports** for modules.  
  *Example:*  
  ```js
  const installTarget = require('../lib/installTargets');
  ```

- **Export Style:**  
  Both CommonJS (`module.exports`) and ES module (`export`) styles are present.  
  *Example (CommonJS):*  
  ```js
  module.exports = function mySkill() { ... };
  ```
  *Example (ES Module):*  
  ```js
  export function mySkill() { ... }
  ```

- **Commit Messages:**  
  Use [Conventional Commits](https://www.conventionalcommits.org/).  
  Prefixes: `fix`, `feat`, `docs`, `chore`  
  *Example:*  
  ```
  feat: add Gemini install target support
  fix: correct agent prompt registration logic
  ```

- **Documentation:**  
  Each skill or agent should have a `SKILL.md` or `.md` documentation file explaining its purpose and usage.

## Workflows

### Add New Skill
**Trigger:** When introducing a new skill for agents or workflows  
**Command:** `/add-skill`

1. Create a new `SKILL.md` file under `skills/`, `.agents/skills/`, or `.claude/skills/`.
2. Document the skill's purpose, usage, and configuration.
3. Optionally update manifests or documentation if the skill is significant.

*Example:*
```
skills/myNewSkill/SKILL.md
```

---

### Add New Agent or Agent Prompt
**Trigger:** When introducing a new agent persona or capability  
**Command:** `/add-agent`

1. Create a new agent definition (e.g., `agents/myAgent.md` or `.opencode/prompts/agents/myAgent.txt`).
2. Register the agent in the relevant configuration file (e.g., `.opencode/opencode.json`).
3. Update `AGENTS.md` or related documentation.

*Example:*
```
agents/supportAgent.md
```

---

### Add or Update Command Workflow
**Trigger:** When introducing or improving a workflow command  
**Command:** `/add-command`

1. Create or update a command file under `commands/` (e.g., `commands/review.md`).
2. Optionally update related documentation or scripts.
3. Address review feedback and refine command logic.

---

### Add Install Target or Adapter
**Trigger:** When supporting a new platform or integration  
**Command:** `/add-install-target`

1. Add new install scripts and documentation under a dot-directory (e.g., `.gemini/`, `.codebuddy/`).
2. Update `manifests/install-modules.json` and relevant schema files.
3. Implement or update `scripts/lib/install-targets/*.js` for the new target.
4. Add or update tests for the install target.

*Example:*
```
.gemini/install.sh
scripts/lib/install-targets/gemini.js
tests/lib/install-targets.test.js
```

---

### Refactor or Collapse Commands to Skills
**Trigger:** When modernizing command logic under the skills architecture  
**Command:** `/refactor-to-skill`

1. Update or remove `commands/*.md` files.
2. Add or update `skills/*/SKILL.md` files.
3. Update documentation (`README.md`, `AGENTS.md`, `WORKING-CONTEXT.md`, etc.).
4. Update manifests if required.

---

### Documentation and Guidance Update
**Trigger:** When clarifying, updating, or adding documentation  
**Command:** `/update-docs`

1. Edit or create documentation files (`README.md`, `WORKING-CONTEXT.md`, `docs/*.md`, etc.).
2. Sync or update guidance in multiple language versions if needed.
3. Optionally update related configuration or manifest files.

---

### CI/CD Workflow Update
**Trigger:** When improving or fixing CI/CD processes  
**Command:** `/update-ci`

1. Edit `.github/workflows/*.yml` files.
2. Update lockfiles (`package-lock.json`, `yarn.lock`) or validation scripts.
3. Update or add test files for CI/CD logic.

---

## Testing Patterns

- **Test Files:**  
  Test files follow the pattern `*.test.js`.

- **Framework:**  
  No specific testing framework detected; structure your tests in standard Node.js or your preferred test runner.

*Example:*
```
tests/lib/install-targets.test.js
```

- **Test Example:**
  ```js
  // install-targets.test.js
  const installTarget = require('../../scripts/lib/install-targets/gemini');

  test('should install Gemini target', () => {
    expect(installTarget()).toBe(true);
  });
  ```

## Commands

| Command            | Purpose                                                        |
|--------------------|----------------------------------------------------------------|
| /add-skill         | Add a new skill module and document it                         |
| /add-agent         | Add a new agent definition or prompt                           |
| /add-command       | Add or update a command workflow                               |
| /add-install-target| Add a new install target or adapter                            |
| /refactor-to-skill | Refactor commands into skill-based modules                     |
| /update-docs       | Update documentation or guidance files                         |
| /update-ci         | Update CI/CD workflows, lockfiles, or validation scripts       |
```
