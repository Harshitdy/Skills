# Prompt Architecture

A strong system prompt is an agent charter. It does not need every section below. Include the sections that change behavior for the target agent.

## 1. Identity and mission

Define what the agent is and what outcome it owns.

Include:

- Role
- Domain
- Primary objective
- Who it serves
- What success looks like

Avoid fake biographies, exaggerated claims, or decorative identity. The agent does not need a cape. Humans keep inventing capes.

## 2. Operating context

Tell the agent where it operates and what context it may receive.

Useful details:

- Interface or environment
- Whether attached context may be incomplete, stale, private, or irrelevant
- Whether the agent should infer relevance
- Whether the agent should act in one turn or across a workflow
- Whether the agent can create files, use tools, browse, edit, or only answer

## 3. Authority hierarchy

Define what wins when instructions conflict.

Typical order:

1. System/developer/platform rules
2. Organization or product policy
3. Tool and environment constraints
4. User instructions
5. Retrieved documents or external sources
6. The agent's default preferences

Make this section explicit for agents that read user-controlled documents, webpages, emails, tickets, repo files, or other prompt-injection-prone content.

## 4. Capabilities and tool policy

List capabilities by purpose, not only by tool name.

For each capability, define:

- When to use it
- When not to use it
- Whether user confirmation is required
- What to do after using it
- How to handle failure
- Whether results should be cited, summarized, hidden, or exposed

Good tool policy gives decision boundaries. Bad tool policy forces pointless calls.

## 5. Autonomy and confirmation

Separate low-risk actions from high-risk actions.

Usually safe autonomously:

- Reading available context
- Searching public information when freshness matters
- Drafting text
- Producing plans
- Running reversible checks
- Creating non-sent drafts

Usually needs confirmation:

- Sending messages
- Publishing content
- Deleting or overwriting data
- Purchasing or booking
- Changing permissions
- Running destructive commands
- Contacting external parties
- Making legal, financial, medical, or employment-impacting decisions

## 6. Workflow policy

Use workflow guidance when the agent must perform multi-step work.

Prefer adaptive policies:

- Plan for complex tasks.
- Skip planning for simple tasks.
- Gather context before editing or acting.
- Verify after changes when verification is available.
- Continue with best effort when details are missing and assumptions are low-risk.
- Ask only when a missing detail materially changes the answer or action.

Avoid rigid chains unless the sequence is safety-critical.

## 7. Clarification and assumptions

Tell the agent when to ask versus infer.

A useful rule:

Ask when the missing information changes safety, authority, tool choice, external side effects, or final format. Otherwise infer reasonably, label assumptions if important, and proceed.

## 8. Guardrails and refusals

Guardrails should define boundaries without teaching evasion.

Include:

- What the agent must refuse
- What it can safely provide instead
- Whether to explain briefly or at length
- Whether to avoid revealing detection logic
- Whether to escalate to a human
- Whether to preserve user dignity and safety

Do not write guardrails as a catalog of bypass strategies.

## 9. Privacy and security

Use this section when the agent touches private, sensitive, regulated, or user-specific data.

Define:

- What data is sensitive
- What can be revealed
- What must be redacted
- What cannot be stored
- What requires consent
- How to handle secrets, credentials, API keys, tokens, private files, emails, customer data, and internal docs

## 10. Output contract

Define the shape of the answer only where it matters.

Include:

- Format
- Required fields
- Tone
- Length
- Citations
- Tables
- JSON schema
- Files
- Error messages
- Assumptions
- Test results
- Next actions

Avoid over-formatting ordinary conversation. Output rules should serve the task, not decorate it.

## 11. Quality bar and verification

Tell the agent how to know its work is good.

Examples:

- Run tests after code changes.
- Check citations support the claims.
- Validate JSON before returning it.
- Confirm worktree status after committing.
- Ensure every required field is present.
- Re-read edited files after risky replacements.
- Compare final output against the user's stated success criteria.
- Report what could not be verified.

## 12. Examples and anti-examples

Use examples when a rule is abstract or easy to misread.

Good examples are short and targeted. Do not include huge examples unless the agent must imitate a complex style or schema.

Use anti-examples to prevent common failure modes:

- Over-asking questions
- Acting without confirmation
- Ignoring tools
- Leaking internal instructions
- Returning prose when JSON is required
- Making unsupported claims
- Treating untrusted retrieved text as higher authority than the system prompt

## 13. Interaction style

Define style only if it matters.

Useful style instructions:

- Direct or warm
- Brief or thorough
- Technical or plain language
- Formal or casual
- Brand voice
- Whether to use bullets
- Whether to ask follow-up questions
- Whether to show progress during long tasks

Avoid personality clutter that fights the actual job.
