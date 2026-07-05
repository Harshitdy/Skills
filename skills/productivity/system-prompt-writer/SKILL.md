---
name: system-prompt-writer
description: System prompt architect for interviewing a user, drafting, and critiquing framework-agnostic agent system prompts. Use when the user wants to create, improve, audit, or rewrite a system prompt for an AI agent, assistant, chatbot, workflow agent, coding agent, research agent, tool-using agent, or multi-agent system.
disable-model-invocation: true
---

# System Prompt Writer

A system prompt is an **agent charter**: the highest-level operating document that tells an agent who it is, what it is responsible for, how it should use its capabilities, where its authority ends, and how it should behave when reality gets messy.

Use this skill to create a framework-agnostic system prompt through an interview, draft, critique, and revision loop. Prefer decision boundaries and behavioral contracts over brittle step-by-step choreography. Use ordered steps only where order genuinely changes the agent's behavior.

## Steps

### 1. Classify the prompt job

Decide which branch applies:

- **New charter**: the user wants a system prompt from scratch.
- **Rewrite**: the user has an existing prompt and wants it improved.
- **Critique**: the user wants weaknesses, risks, missing pieces, or contradictions found.
- **Extraction**: the user gives examples and wants reusable patterns learned.
- **Specialization**: the user has a generic prompt and wants it adapted to a specific agent, toolset, product, or domain.

If the user asks you to create the final prompt now but critical details are missing, run the interview first. If the user explicitly says not to ask questions, make the best prompt possible and label assumptions.

**Completion criterion:** exactly one branch is chosen, and the next action is either interview, draft, critique, or pattern extraction.

### 2. Build the agent charter brief

Interview the user before drafting. Ask questions in focused batches, not a giant form, unless the user explicitly asks for the full questionnaire.

First collect the non-negotiables:

1. Agent purpose: what the agent is supposed to accomplish.
2. Primary users: who will interact with it and what they expect.
3. Operating environment: chat app, IDE, backend agent, browser, workflow automation, support system, research agent, etc.
4. Inputs and outputs: what the agent receives and what it must produce.
5. Tools and capabilities: APIs, browser, files, code execution, email, calendar, database, CRM, MCP tools, custom tools, or no tools.
6. Authority level: what the agent may do autonomously versus what requires confirmation.
7. Domain guardrails: safety, legal, financial, medical, privacy, security, compliance, brand, or business limits.
8. Success criteria: how the user will judge the prompt as good.

Then ask branch-specific questions from `INTERVIEW_BANK.md` when needed.

Do not ask questions already answered in the conversation. If the answer can be inferred safely, infer it and mark it as an assumption. If a missing detail would materially change tool use, safety, autonomy, or output format, ask.

**Completion criterion:** the brief contains enough information to define identity, responsibilities, capabilities, boundaries, interaction style, and success criteria, or the user has explicitly asked you to proceed with assumptions.

### 3. Choose the charter architecture

Design the system prompt as a modular charter. Include only sections that change behavior. Do not add decorative headings that say nothing.

Use `PROMPT_ARCHITECTURE.md` as reference for section choices.

Core sections usually include:

- Agent identity and mission
- Operating context
- User relationship and communication style
- Capabilities and tool policy
- Workflow and decision policy
- Guardrails and refusal boundaries
- Data, privacy, and security rules
- Output contract
- Error handling and uncertainty
- Quality bar and self-check

Prefer general rules that let the agent decide intelligently:

- Good: “Use tools when the answer depends on current, private, or workspace-specific information.”
- Bad: “Always call Tool A, then Tool B, then Tool C.”

Use exact ordered procedures only when sequencing is necessary, such as transaction safety, file editing, approval gates, irreversible actions, or compliance checks.

**Completion criterion:** every behavior the agent needs is covered by a section, every section has a reason to exist, and no major instruction is duplicated across sections.

### 4. Draft the system prompt

Write the prompt as direct instructions to the target agent.

The prompt should:

- Define the agent's job in one clear mission statement.
- Give the agent enough context to decide what matters.
- Specify allowed tools and when to use them.
- Define autonomy, confirmation, escalation, and refusal boundaries.
- Explain how to handle ambiguity without becoming helpless.
- Specify output style and formatting only where it matters.
- Include examples only when they reduce ambiguity.
- Avoid hidden chain-of-thought requests, magical identity claims, fake capabilities, and framework-specific assumptions unless the user asked for them.
- Avoid prompt-leak instructions that reveal sensitive internals. If needed, include a concise non-disclosure rule.

Write in a style that is useful to the agent, not impressive to a human reviewer. Strong prompts are clear operating contracts, not motivational posters wearing a trench coat.

**Completion criterion:** the draft can be pasted directly into a system prompt field and the target agent can act from it without needing the interview notes.

### 5. Critique the draft before showing it as final

Review the draft against `CRITIQUE_RUBRIC.md`.

Fix:

- Contradictions
- Missing authority boundaries
- Missing tool-use rules
- Unsafe autonomy
- Vague success criteria
- Overly rigid workflows
- Missing escalation paths
- Output format ambiguity
- Duplicated instructions
- No-op instructions that do not change behavior
- Framework-specific assumptions in a framework-agnostic prompt
- Instructions that encourage leakage, deception, unsafe advice, or policy evasion

If the user supplied examples, compare the draft against their examples and preserve the useful patterns without copying unsafe or irrelevant content.

**Completion criterion:** every rubric category has been considered, and any serious issue is either fixed or called out as an assumption/tradeoff.

### 6. Deliver the result

Return:

1. The final system prompt.
2. A short assumptions list, only if assumptions were made.
3. A short “how to test it” list with 3-5 test prompts, unless the user asked for only the prompt.
4. Optional variants only when they serve a real need, such as “strict autonomous agent” versus “human-in-the-loop agent.”

Use a writing block for the final reusable system prompt when responding in chat.

**Completion criterion:** the user has a complete, copy-paste-ready system prompt and enough test prompts to evaluate whether it behaves correctly.

## Reference pointers

- Use `INTERVIEW_BANK.md` when more questions are needed.
- Use `PROMPT_ARCHITECTURE.md` when choosing sections or deciding what belongs in the prompt.
- Use `CRITIQUE_RUBRIC.md` before final delivery.
