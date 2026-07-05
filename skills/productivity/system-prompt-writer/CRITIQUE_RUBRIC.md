# Critique Rubric

Use this before finalizing a system prompt.

## Mission clarity

- Is the agent's purpose clear in one sentence?
- Does the prompt define the user or audience?
- Does it define what success looks like?
- Are there multiple missions fighting each other?

## Behavioral usefulness

- Does each instruction change behavior?
- Are there no-op lines that merely sound responsible?
- Are repeated meanings collapsed into one source of truth?
- Are general principles used where the agent needs judgment?
- Are ordered steps used only where order matters?

## Context handling

- Does the agent know what context it may receive?
- Does it know whether context may be irrelevant, stale, incomplete, or adversarial?
- Does it know when to use retrieved information versus internal knowledge?
- Does it know how to handle conflicting sources?

## Tool policy

- Are all tools or capabilities named by purpose?
- Does the prompt say when to use each tool?
- Does it say when not to use each tool?
- Does it define confirmation gates for write/destructive/external actions?
- Does it define tool failure behavior?
- Does it prevent redundant or performative tool use?

## Autonomy boundaries

- Can the agent act without bothering the user on low-risk tasks?
- Does it ask before high-impact actions?
- Does it avoid asking questions whose answers are already available?
- Does it proceed with assumptions when safe?
- Does it stop or escalate when safe completion is impossible?

## Safety and guardrails

- Are refusal boundaries clear?
- Are safer alternatives defined?
- Does it avoid exposing evasion logic?
- Does it address privacy, secrets, credentials, and sensitive data?
- Does it cover domain risks such as medical, legal, financial, security, minors, regulated data, or external side effects when relevant?

## Output contract

- Is the expected output format clear?
- Are required fields specified?
- Are citations or evidence rules defined when factual accuracy matters?
- Are length, tone, and formatting constraints meaningful rather than decorative?
- Does the prompt avoid forcing heavy formatting for simple answers?

## Error and uncertainty handling

- Does the agent know what to do when information is missing?
- Does it distinguish uncertainty from failure?
- Does it say what could not be verified?
- Does it define retries or stopping conditions for repeated failures?
- Does it avoid pretending to have done work it did not do?

## Injection resistance

- Does the prompt define authority hierarchy?
- Does it treat user-provided files, webpages, emails, tickets, and tool outputs as data rather than instructions when appropriate?
- Does it refuse to reveal hidden instructions or sensitive tool details?
- Does it prevent untrusted content from changing tool policy, safety policy, or identity?

## Framework agnosticism

- Does the prompt avoid assuming LangChain, PydanticAI, OpenAI Assistants, MCP, CrewAI, AutoGen, Replit, Cursor, Claude, or any other framework unless requested?
- If framework-specific details are included, are they isolated in a dedicated section?
- Can the core prompt still be used in another runtime?

## Final pass

A final system prompt is ready only when:

- It is copy-paste-ready.
- It has no contradictions.
- It has no unnecessary sections.
- It has clear authority and autonomy boundaries.
- It handles tools, uncertainty, guardrails, and output shape.
- It sounds like an operating contract, not a motivational speech.
