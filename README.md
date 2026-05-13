# Refactor Legacy Code

[![skills.sh](https://skills.sh/b/peizh/refactor-legacy-code)](https://skills.sh/peizh/refactor-legacy-code)

An agent skill for making safe, incremental changes in large legacy codebases.

It helps an agent identify change points, find test points, choose seams, write characterization tests, break dependencies only where needed, and refactor inside newly protected areas.

## Install

List the skill without installing:

```bash
npx skills add peizh/refactor-legacy-code --list
```

Install and let the CLI pick the detected agent:

```bash
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code
```

Install globally for the detected agent without prompts:

```bash
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -g -y
```

Install for a specific agent:

```bash
# Codex
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a codex

# Claude Code
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a claude-code

# Cursor
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a cursor

# Windsurf
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a windsurf

# GitHub Copilot
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a github-copilot

# Gemini CLI
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a gemini-cli

# OpenCode
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a opencode
```

Install for multiple agents:

```bash
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code -a codex -a claude-code -a cursor
```

Install for all supported agents detected by the CLI:

```bash
npx skills add peizh/refactor-legacy-code --skill refactor-legacy-code --agent '*'
```

## Use

Example prompt:

```text
Use $refactor-legacy-code to plan and execute a safe change in this large legacy codebase.
```

The skill is most useful when:

- code is poorly tested or hard to instantiate
- a method, class, module, or subsystem is too large to change confidently
- external APIs, globals, statics, construction, or framework dependencies block tests
- a bug fix or feature must preserve existing behavior
- repeated changes suggest a missing boundary or ownership point

## Structure

```text
.
├── SKILL.md
├── references/
│   ├── change-workflow.md
│   └── dependency-breaking.md
└── agents/
    └── openai.yaml
```

`SKILL.md` contains the core workflow. Reference files are loaded only when a task needs deeper guidance.

## Notes

This skill is an original workflow artifact inspired by common legacy-code refactoring practice. It does not include or redistribute book text, examples, or copyrighted source material.

See [NOTICE.md](NOTICE.md) for attribution and copyright boundaries.
