# Agent Skills

Reusable AI agent skills packaged as a Claude marketplace with two plugins.

## Plugins

### think-like-fable5-plugin

Verification-first reasoning for correctness-critical tasks.

Invocation:

```text
/think-like-fable5-plugin:think-like-fable5
```

### system-prompt-writer-plugin

Framework-agnostic system prompt interviewing, drafting, and critique workflow.

Invocation:

```text
/system-prompt-writer-plugin:system-prompt-writer
```

## Install

Add the marketplace:

```text
/plugin marketplace add Harshitdy/think-like-fable5
```

Install either plugin:

```text
/plugin install think-like-fable5-plugin@think-like-fable5
/plugin install system-prompt-writer-plugin@think-like-fable5
```

## Repo Structure

```text
.
├── .claude-plugin/
│   └── marketplace.json
└── plugins/
    ├── think-like-fable5-plugin/
    │   ├── .claude-plugin/
    │   │   └── plugin.json
    │   └── skills/
    │       └── think-like-fable5/
    │           └── SKILL.md
    └── system-prompt-writer-plugin/
        ├── .claude-plugin/
        │   └── plugin.json
        └── skills/
            └── system-prompt-writer/
                ├── CRITIQUE_RUBRIC.md
                ├── INTERVIEW_BANK.md
                ├── PROMPT_ARCHITECTURE.md
                └── SKILL.md
```

## License

MIT
