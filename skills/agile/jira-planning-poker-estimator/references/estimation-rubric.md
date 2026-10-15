# Estimation rubric

## Default Planning Poker anchors (calibrate with the team)
- 1: tiny, well-understood change, negligible dependencies.
- 2: small, localized change with straightforward verification.
- 3: modest change with some branching or testing considerations.
- 5: multi-part change or moderate integration uncertainty.
- 8: complex cross-component work, substantial verification or unknowns.
- 13: high uncertainty or broad impact; consider splitting.
- 21: likely too large; split or spike before commitment.

These are relative anchors, not fixed hours or a universal standard.

## Effort estimation
Estimate each work package as low–likely–high hours where useful. Sum corresponding bounds per role and scenario. Keep human review, prompt preparation, setup, CI, test execution, defect fixing, and integration effort visible in Claude-assisted estimates. Explain any change in points independently of hours.

## Claude leverage candidates
Dev: repo navigation, locating analogous implementations, drafting boilerplate, unit-test scaffolding, refactoring proposals, documentation, PR summaries.
QA: acceptance-criteria expansion, scenario matrices, boundary/negative cases, Playwright draft scripts, synthetic test-data helpers, failure triage summaries.
Never assume automation replaces environment readiness, domain judgment, exploratory testing, security review, or approval.

## Confidence
High: requirements and impacted code known, comparable completed work.
Medium: a few bounded unknowns or dependencies.
Low: unclear acceptance criteria, unknown integration, missing access or major architectural uncertainty.

## Savings calculation
For each role, savings hours = baseline hours − assisted hours.
Savings % = (baseline − assisted) / baseline × 100, only if baseline > 0.
Use same-scope comparisons and label estimates as hypotheses until validated against actual outcomes.
