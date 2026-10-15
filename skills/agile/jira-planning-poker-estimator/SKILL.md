---
name: jira-planning-poker-estimator
description: Draft evidence-based Planning Poker estimates for a shared Jira ticket, separately comparing developer and QA effort with and without Claude Code. Use when asked for story points, effort breakdowns, sprint planning estimates, or AI-assisted estimation.
---
# Jira Planning Poker Estimator

## Purpose
Analyze a Jira story, bug, task, or epic and produce a meeting-ready, defensible estimation draft for **Development** and **QA**, each with **without Claude** and **with Claude** scenarios.

## Inputs
Accept pasted Jira description, link (only retrieve if accessible), screenshot, or attached ticket. Read title, issue type, description, acceptance criteria, linked issues, technical notes, impacted services, environments, definition of done, and known dependencies. Do not claim to have read inaccessible Jira links. Ask for missing critical details, or proceed with explicitly labeled assumptions.

## Workflow
1. Summarize ticket scope and observable acceptance criteria; distinguish facts, inferences, and unknowns.
2. Identify implementation work packages (discovery, design, code, integrations, migration, review, unit/integration tests, deployment support) and QA packages (analysis, test design, data/environment setup, automation, manual/exploratory testing, regression, defect retest, reporting).
3. Estimate **without Claude** first as a baseline for each role, with per-task hours or ranges, reasons, dependencies, and risks.
4. Estimate **with Claude** using concrete Claude Code workflows available to the team. Reduce only eligible subtasks, accounting for prompt/context setup, output review, debugging, test execution, and security checks. Do not assume Claude can access Jira, code, environments, or credentials unless explicitly confirmed.
5. Provide separate **Dev** and **QA** Planning Poker points for both scenarios using the team's scale, default Fibonacci 1, 2, 3, 5, 8, 13, 21. Points reflect relative complexity, uncertainty, and risk, **not hours converted to points**. Keep points unchanged when AI only speeds execution but does not change underlying complexity. Recommend splitting very large stories.
6. Calculate effort savings using comparable hour ranges and show the calculation. Savings are conditional estimates, not guaranteed outcomes. Never claim an arbitrary fixed productivity percentage.
7. Report acceptance-criteria gaps, blockers, testing strategy, security/privacy implications, assumptions, confidence (low/medium/high), and questions for grooming.
8. End with a concise, copy-ready Jira estimation comment and an explicit reminder that team consensus decides final points.

## Mandatory output format
### Ticket snapshot
Key, title, type, scope, acceptance criteria, assumptions, unknowns.

### Planning Poker recommendation
| Role | Without Claude (points) | Without Claude (hours/range) | With Claude (points) | With Claude (hours/range) | Confidence |
|---|---|---|---|---|---|
| Dev | ... | ... | ... | ... | ... |
| QA | ... | ... | ... | ... | ... |

### Development — without Claude
Breakdown table: work item, effort, **why**.

### Development — with Claude
Breakdown table: work item, effort, **how Claude helps**, remaining human validation, and any added AI overhead.

### QA — without Claude
Breakdown table: work item, effort, **why**.

### QA — with Claude
Breakdown table: work item, effort, **how Claude helps**, remaining manual verification, and any added AI overhead.

### Other details
Dependencies, out-of-scope items, risk and uncertainty, test matrix, environments, definition of done, security considerations, blockers, clarifying questions, and conditions under which estimates change.

### Savings analysis
Dev and QA baseline vs assisted hours; absolute and percentage differences only when inputs support them. Do not add Dev and QA points together unless team policy explicitly permits.

### Planning Poker talking points
Explain the recommendation and what would change the estimate; note disagreement points for team discussion.

### Copy-ready Jira comment
Short summary with role-by-role points, hour ranges, rationale, AI leverage, risks, and assumptions.

## Guardrails
- Do not equate story points with calendar duration.
- Do not promise 100% test coverage or defect-free output.
- Treat all generated code and tests as untrusted until reviewed and executed.
- Never paste secrets, credentials, customer data, or restricted source into unapproved AI tools.
- Claude is an assistant, not an autonomous approval authority.
- Mark every unsupported detail as an assumption and use ranges for uncertain work.
- For bugs, include reproduction and root-cause uncertainty.
- For data changes, include migration, rollback, and data validation.
- For UI changes, include accessibility, responsive behavior, and cross-browser coverage.
- When the team uses one combined story-point vote, offer a single team consensus recommendation separately; do not mechanically sum role votes.

See [estimation rubric](references/estimation-rubric.md) and [report template](assets/estimate-template.md).
