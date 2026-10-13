---
name: product-debate
license: MIT
description: "Pressure-test product hypotheses through six adversarial turns, optionally eight, then define a minimum V1, success criteria, and validation plan. Use for /ProductDebate, red-team product reviews, and proceed-versus-hold decisions. Do not load for ordinary feature brainstorming without a requested debate."
metadata:
  version: '1.0'
  author: swapna-kutcharlapati
---

# Product Debate

Run six turns between two simulated perspectives. Add one matched pair only under the extension rule. Explain which argument prevailed without treating it as validation. The user owns the scorecard and investment verdict.

## Workflow

1. Read `references/rules.md` and `references/execution.md`. Ask one intake for missing principles or taste, core hypotheses, and evidence, then wait. Skip answered questions or honor an explicit skip. Declare the US default when jurisdiction is absent. Freeze the charter.
2. Read `references/proponent.md` for Turns 1, 3, and 5, plus optional Turn 7. Read `references/devils-advocate.md` for Turns 2, 4, and 6, plus optional Turn 8. Follow the shared budgets, claim IDs, evidence rules, acceptance criteria, and question handoffs. Retain the actual outputs.
3. After Turn 6, apply the stopping rule in `references/rules.md`. Stop when the hypothesis, V1, criteria, safety controls, and next test are stable. Add Turns 7 and 8 only for a consequential unresolved objection reasoning could address, or an explicit user request. Record why. Never exceed eight turns or add closing speeches.
4. Read `references/validation-package.md`. Build the objection ledger, minimum V1 and exclusions, evidence backlog, definition of success, metrics, guardrails, and requirement-linked launch plan. Recommend research when no coherent V1 survives.
5. Read `templates/readout.md`. Follow all seven sections in plain English, with meanings before optional labels in parentheses. Explain which argument prevailed, what remains unproven, and the first validation action. Introduce no new evidence in synthesis and do not assign user scores.
6. Read `references/rubric.md` and `templates/scorecard.md`. Share a Markdown report with the charter, actual six- or eight-turn transcript, stopping decision, complete material tables, compact rubric, and blank scorecard. Offer "Show full debate" and "Return to summary." Retrieve the retained transcript rather than regenerate it.
7. Once the user scores or chooses a verdict, read the matching template in `templates/verdict-proceed.md`, `templates/verdict-pilot.md`, `templates/verdict-hold.md`, or `templates/verdict-reframe.md`. Preserve uncertainty and gate restrictions.
8. Only for a requested prototype handoff after scope settles, read `templates/prototype-prompt.md`. Match the V1 exactly and default to synthetic data.

## Completion checks

- Verify six alternating turns or eight with a recorded extension reason, never seven.
- Verify questions in Turns 4 and 5 are answered first in Turns 5 and 6. Optional Turn 7 asks one question answered in Turn 8. No question spills past the last turn.
- Keep disagreements, concessions, missing evidence, and user constraints visible. Agreement is not validation.
- Use no em dashes, colons in prose, or semicolons in user-facing output.
- Give each V1 capability a necessary outcome, test, measurement, or safety rationale.
- Separate success criteria from metrics. Include meaningful usage and data sufficiency when relevant. Label provisional targets and define denominators, windows, and baselines.
- Preserve intake, US default, seven-section readout, and full-transcript access.

## Example

For an unrecognized-charge agent, run six turns. Stop when the narrowed V1 and resolving tests are stable, even if private cost data remain unknown. Extend to eight only if a consequential new objection needs a matched response.

## Package license

Read `LICENSE` when explaining reuse permissions and preserve it when sharing the package. Read `README.md` when the user asks how to use or install the skill.
