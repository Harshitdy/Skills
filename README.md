# Agent Skills

Reusable AI agent skills for building better agents, prompts, workflows, and coding-agent behavior.

## Available Skills

### system-prompt-writer

A framework-agnostic skill that interviews the user, gathers requirements, drafts a system prompt, critiques it, and produces a high-quality final system prompt for an AI agent.

It helps define:

- agent purpose
- users
- operating context
- tools and capabilities
- autonomy boundaries
- guardrails
- privacy and security rules
- output format
- success criteria
- test prompts

## Install

List available skills:

```bash
npx skills@latest add Harshitdy/Skills --list
```

Install interactively:

```bash
npx skills@latest add Harshitdy/Skills
```

Install only `system-prompt-writer`:

```bash
npx skills@latest add Harshitdy/Skills --skill system-prompt-writer
```

Install globally for Codex:

```bash
npx skills@latest add Harshitdy/Skills --skill system-prompt-writer -g -a codex -y
```

Install globally for Claude Code:

```bash
npx skills@latest add Harshitdy/Skills --skill system-prompt-writer -g -a claude-code -y
```

Install globally for Cursor:

```bash
npx skills@latest add Harshitdy/Skills --skill system-prompt-writer -g -a cursor -y
```

Use without installing:

```bash
npx skills@latest use Harshitdy/Skills --skill system-prompt-writer
```

## How to Use

After installing, ask your coding agent:

```text
Use the system-prompt-writer skill. Interview me first, then create the best possible system prompt for my agent.
```

For a coding-agent-specific prompt:

```text
Use the system-prompt-writer skill to interview me and create a system prompt for a coding agent that works on my codebase safely.
```

## Repo Structure

```text
skills/
└── productivity/
    └── system-prompt-writer/
        ├── SKILL.md
        ├── INTERVIEW_BANK.md
        ├── PROMPT_ARCHITECTURE.md
        └── CRITIQUE_RUBRIC.md
```

## Direct Skill Path

The main skill file is here:

```text
skills/productivity/system-prompt-writer/SKILL.md
```
