# Agent Skills

Reusable AI agent skills for building better agents, prompts, workflows, and coding-agent behavior.

## Skills

### system-prompt-writer

A framework-agnostic skill that interviews the user, gathers requirements, drafts a system prompt, critiques it, and produces a high-quality final system prompt for an AI agent.

It helps define:

- agent purpose
- users
- tools and capabilities
- autonomy boundaries
- guardrails
- privacy and security rules
- output format
- success criteria
- test prompts

## Install

Install the skill:

```bash
npx skills@latest add Harshitdy/Skills --skill system-prompt-writer
```

List installed skills:

```bash
npx skills@latest list
```

Use without installing:

```bash
npx skills@latest use Harshitdy/Skills --skill system-prompt-writer
```

## How to Use

This skill has model invocation disabled, so you need to invoke it explicitly.

If your agent supports slash skill commands, use:

```text
/system-prompt-writer
```

Then say:

```text
Interview me first, then create the best possible system prompt for my agent.
```

If your agent does not support slash commands, type:

```text
Use the system-prompt-writer skill. Interview me first, then create the best possible system prompt for my agent.
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

## Skill Path

```text
skills/productivity/system-prompt-writer/SKILL.md
```

## License

MIT
