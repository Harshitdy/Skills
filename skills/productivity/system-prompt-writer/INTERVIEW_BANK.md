# Interview Bank

Use this file only when the initial brief is incomplete or the user asks for a deeper interview.

Ask the smallest useful batch first. For most users, ask 6-10 questions, then continue only if the answers reveal important missing details. For complex agents, ask in rounds.

## Foundation

- What should the agent accomplish in one sentence?
- Who will use this agent?
- What problem does it solve better than a normal chat assistant?
- What does a successful conversation or run look like?
- What should the agent never do, even if the user asks?
- What should the agent do when the user request is unclear?

## Operating context

- Where will the agent run: chat, IDE, browser, backend job, CRM, Slack, support desk, workflow automation, mobile app, or something else?
- Will it operate synchronously in conversation, asynchronously in the background, or both?
- Will it interact with one user, many users, customers, employees, developers, analysts, or admins?
- Does it need to preserve state or memory across turns or sessions?
- Does it need to follow organization, team, or product-specific policies?

## Tools and capabilities

- What tools can the agent call?
- What does each tool do?
- Which tools read private data?
- Which tools write, modify, delete, purchase, publish, send, or trigger external effects?
- Which tool calls require confirmation?
- Which tool calls are safe to perform autonomously?
- What should the agent do when a tool fails?
- What should the agent do when tool results conflict with the user or with its internal knowledge?
- Should the agent mention tools to the user or describe actions naturally?

## Data and source authority

- What sources should the agent trust most?
- Should it browse the web for current information?
- Should it use internal docs, uploaded files, databases, emails, calendars, repos, tickets, or CRM records?
- How should it cite sources, if citations are needed?
- What should it do when sources disagree?
- What data is sensitive, private, regulated, or confidential?
- What should never be stored, logged, exposed, or sent to external services?

## Autonomy and approval

- Can the agent take action without asking?
- Which actions are reversible?
- Which actions are irreversible or high-impact?
- When should the agent ask for confirmation?
- When should it refuse?
- When should it escalate to a human?
- Should it optimize for speed, safety, completeness, or minimal user interruption?

## Workflow behavior

- Should the agent plan before acting?
- Should it show progress updates?
- Should it maintain a checklist?
- Should it ask clarifying questions or make assumptions?
- Should it complete partial work when details are missing?
- How many retry attempts are acceptable after failures?
- What should it do after repeated failures?
- Should it verify outputs with tests, linting, previews, citations, screenshots, or sanity checks?

## Output contract

- What format should the agent usually return?
- Does the user need JSON, Markdown, code, tables, files, summaries, emails, reports, or UI-ready content?
- Should responses be concise or detailed?
- Should the agent include reasoning summaries, assumptions, sources, confidence, risks, or next steps?
- Are there banned phrases, formatting rules, tone rules, or brand voice constraints?
- Should outputs be machine-readable, human-readable, or both?

## Domain guardrails

- Does the agent touch medical, legal, financial, employment, education, child safety, security, privacy, or regulated domains?
- Does it interact with minors or vulnerable users?
- Could it enable fraud, abuse, surveillance, deception, data exfiltration, unsafe code, or harmful physical actions?
- What should safe refusal look like?
- What safer alternatives should it offer after refusal?
- Are there jurisdiction-specific rules, company policies, or compliance obligations?

## Coding-agent questions

- What languages, frameworks, package managers, and test commands matter?
- Should the agent edit files directly or only suggest changes?
- Should it prefer existing patterns over new abstractions?
- Should it run tests, lint, type checks, builds, or app previews?
- Should it commit changes?
- Should it obey repo instruction files such as AGENTS.md, README, CONTRIBUTING, or style guides?
- Should it modify database schemas or migrations?
- Should it avoid destructive commands?
- Should it ask before installing dependencies?

## Research-agent questions

- What topics does the agent research?
- Which sources are allowed or preferred?
- How current must the answer be?
- Does it need citations?
- Should it compare sources?
- Should it distinguish facts, claims, inferences, and uncertainty?
- Should it produce briefs, tables, memos, leads, recommendations, or raw notes?

## Sales/support-agent questions

- Who is the target persona?
- What product, service, or offer is the agent representing?
- What claims are approved?
- What claims are forbidden?
- Should the agent qualify leads, answer objections, draft outreach, update CRM, or create tickets?
- What tone should it use with prospects or customers?
- When should it hand off to a human?

## Memory-agent questions

- What should the agent remember?
- What should it never remember?
- Should it ask before saving memory?
- How should it handle corrections to remembered facts?
- How should it distinguish durable preferences from temporary task details?
