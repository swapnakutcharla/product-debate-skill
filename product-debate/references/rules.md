# Shared Rules

## Intake

Before Turn 1 or substantive research, inspect what the user already supplied. For a new invocation, ask the following missing items in one message with at most three focused questions, then wait.

1. What guiding principles or product taste should shape the idea, including any non-negotiable boundaries?
2. What are the core hypotheses you want tested, and what would disprove them?
3. What evidence have you gathered, including evidence against the idea, or are we starting without evidence?

Accept "no preference," "help me frame the hypotheses," "no evidence yet," and an explicit request to skip intake. Do not require evidence or taste to exist. Skip any item already clearly answered. If all three are supplied, proceed without asking redundant questions.

If the user asks to skip, propose a testable hypothesis, note absent taste and evidence, and continue with labeled assumptions. When rerunning the same idea, reuse completed intake unless new input changes it. Do not ask these product-intake questions when the user is editing the skill itself.

Combine clarification of a missing product or target customer with these questions rather than starting repeated intake rounds. Other absent fields become declared assumptions. Do not invent facts.

| Field | Description | If missing |
|---|---|---|
| `proposal` | One-paragraph description of the product or feature | Required. The debate cannot start without it. |
| `customer` | Target customer and segment | Becomes an assumption |
| `alternative` | Status quo or incumbent the customer uses today | Becomes an assumption |
| `hypotheses` | Core customer, causal, adoption, or business propositions the user wants tested, including falsifiers | Ask in the intake. If the user wants help or skips, propose a testable hypothesis and label it unconfirmed. |
| `evidence` | Supporting and contradictory evidence, dates, sources, sample, and segment when known | Ask in the intake. Accept no evidence. Distinguish supplied assertions from independently verified material. |
| `stage` | Idea, prototype, launched, or scaling | Defaults to "idea" |
| `monetization` | Pricing and revenue model | Becomes an assumption |
| `horizon` | Decision time frame, for example a 12-month bet | Defaults to 12 months |
| `jurisdictions` | Markets and regulatory regimes in scope | Default to the United States. State "We assume a US launch unless you specify otherwise." Mark the default as an assumption, not user-supplied evidence. |
| `constraints` | User-stated limits on budget, team, ethics, or strategy | Bind when present |
| `taste` | Guiding principles, quality preferences, and what good looks like in the user's words | Ask in the intake. The answer is optional. Record no preference or a skip without inventing taste. Put explicit non-negotiable boundaries in `constraints`. |

**Taste rules:**
- Treat taste as an input to the debate, not a binding constraint on the verdict. Agents may challenge it. The user adjudicates it.
- The Proponent uses taste to sharpen positioning and the V1. The Devil's Advocate uses taste to spot conflicts between the user's instincts and the evidence.
- When taste conflicts with evidence, surface the conflict in the synthesis. Do not silently resolve it.
- Treat explicit non-negotiable user boundaries as constraints, not merely preferences the agents can ignore. Challenge feasibility or a conflicting boundary openly rather than silently violating it.
- Default country does not establish applicable state law, product coverage, or legal approval. Identify consequential state or product distinctions when relevant. Do not hold every idea solely because the user omitted a country after this default is applied.

## Evidence rules (both agents)

Every substantive sentence carries a claim ID and an evidence tag.

**Claim IDs.** Number Proponent claims `P-01, P-02, …` in order of first appearance. Number Devil's Advocate claims `D-01, D-02, …`. Rebuttals must cite the exact claim they attack, for example "Rebutting D-03."

**Evidence tags:**

| Tag | Meaning | Rule |
|---|---|---|
| `[FACT-S]` | Supplied by the user in intake | Treat as supplied, not verified. User-stated goals and constraints bind. Respectfully challenge the accuracy, scope, or applicability of supplied factual assertions. Retag supplied projections as `[ASSUME]` or `[EST]`. |
| `[FACT-V]` | Externally verified | Must carry a citation. Never invent sources. |
| `[ASSUME]` | Stated assumption | Must be falsifiable. State what breaks it. |
| `[EST]` | Estimate | Must show the arithmetic or basis. |
| `[UNK]` | Unknown | Must state what evidence would resolve it. |

**Shared baseline.** Both agents use identical definitions of CAC, LTV, payback period, gross margin, and churn, and the same horizon, currency, and scenario set. Disputing a number requires disputing its inputs, not its label.

## Prompt assembly

For the default simulated run, keep the perspectives distinct without implying independent models. For explicitly requested separate-agent execution, each agent receives only its own role prompt.

**Each agent's system message holds:**
1. Shared evidence rules (this file, Sections "Evidence rules" and "Turn-taking protocol").
2. Its role prompt (`references/proponent.md` or `references/devils-advocate.md`), with global turn numbers and word budgets embedded.
3. Turn-taking constraints (Section "Turn-taking protocol" below).

**Each agent also receives as context:**
4. The frozen debate charter, including the user's taste when supplied.
5. Turn context. Global turn number, phase, word budget, evidence ledger, and all previously posted turns.

## User-facing punctuation rules

Apply these rules to the debate transcript, moderator synthesis, validation package, scorecard, and all verdict templates the user sees.

- **Do not use em dashes (—).** Use commas, parentheses, or restructure the sentence.
- **Do not use colons (:) in prose.** Use them only inside Markdown table syntax, Markdown link syntax, and the pipe-delimited claim ID format (for example "P-01. Claim text").
- **Do not use semicolons (;).** Split into separate sentences or use a conjunction.
- Restructure sentences rather than substitute other punctuation that creates the same problem. Prefer short, direct sentences.
- Keep the Markdown table and link syntax intact. Do not break valid Markdown to avoid a colon.

## Turn-taking protocol

Use the concise budget by default. Use the deeper budget only when requested. This table is the single authority for word budgets.

| Global turn | Speaker | Phase | Concise words | Deeper words | Constraints |
|---|---|---|---|---|---|
| 1 | Proponent | Opening | 150–220 | 300–500 | Strongest credible case. State assumptions and conditions worth testing. |
| 2 | Devil's Advocate | Challenge | 150–220 | 300–500 | Strongest objections and explicit acceptance criteria. Do not repeat the opening. |
| 3 | Proponent | Revised hypothesis and V1 | 80–130 | 150–300 | Address the objections by ID, revise scope, and concede. Add at most 2 new claims. |
| 4 | Devil's Advocate | Test the revision | 100–150 | 150–300 | Identify what remains unresolved. Ask exactly one direct question on the highest-impact remaining issue. Add at most 2 new claims. |
| 5 | Proponent | Resolve and propose the experiment | 100–160 | 150–300 | Answer Turn 4 first, including arithmetic when relevant. Specify tests, concessions, and falsifiers. Ask exactly one question about conditional acceptance. |
| 6 | Devil's Advocate | Conditional assessment | 100–160 | 150–300 | Answer Turn 5 first. Accept, reject, or specify missing conditions against the original criteria. State remaining blockers and what would change the assessment. Ask no new question. |
| 7 | Proponent | Optional targeted revision | 80–130 | 150–300 | Only under the extension rule. Address the named unresolved issue with a concrete revision or reasoning. Ask exactly one targeted question. |
| 8 | Devil's Advocate | Optional final assessment | 80–130 | 150–300 | Answer Turn 7 first. Assess what changed and what still requires evidence. Ask no new question. |

### Rules

1. **Strict alternation, fixed order.** No agent speaks out of turn. No agent gets the last word twice.
2. **Information symmetry.** Each agent sees the frozen debate charter, the evidence ledger, and all prior turns. Neither sees the other's draft before it posts.
3. **No separate closing speeches.** Put surviving arguments, concessions, and falsifiers into the final matched exchange. Evidence and labeled estimates may inform executed turns, but synthesis introduces no new evidence.
4. **Question handoffs close within the executed debate.** Turn 4 asks exactly one question answered first in Turn 5. Turn 5 asks exactly one question answered first in Turn 6. Turn 6 asks no new question. If extended, Turn 7 asks exactly one question answered first in Turn 8. Turn 8 asks no new question.
5. **Acceptance criteria come from the Devil's Advocate in Turn 2 and stay visible.** State what justifies a bounded test and what blocks it. Record any later change with its reason.
6. **One optional extension, eight total turns maximum.** Apply the stopping rule below after Turn 6. The moderator may add the single matched pair when that rule justifies it, or honor an explicit request for eight turns. Record the reason before Turn 7. Never add a lone seventh turn or a second extension.
7. **Concession log.** The moderator records every conceded claim ID in the synthesis.
8. **Stop condition.** End after Turn 6 by default, or Turn 8 after one justified or requested extension. Neither debating agent can extend itself. Requests for broader new evidence or further debate after eight turns require a new scoped run, not silent extra turns.

### Stopping rule after Turn 6

Check whether another exchange could materially change the hypothesis or segment, minimum V1 or exclusions, acceptance criteria, safety controls, or the next validation test.

- Stop at six when those elements are stable and remaining disagreements require customer evidence, private data, integration access, or qualified review. Unknowns are valid outputs, not reasons to argue indefinitely.
- Extend to eight when a consequential objection remains unanswered and a matched revision and challenge can reasonably resolve it or change one of those elements.
- An explicit user request for eight turns may reserve the pair for the strongest unresolved issue or failure scenario. Do not fabricate disagreement to fill it.
- If the user explicitly requests six only, honor that limit and disclose any unresolved objection in the readout.
- Record the decision, issue if extended, and expected decision impact in the report. After Turn 8, preserve unresolved matters and stop.

Length and depth are separate. A deeper research or longer-transcript request does not automatically require more than six turns.

## User-facing readout (after the synthesis)

Follow the seven-section structure in `templates/readout.md`. Explain the meaning in full sentences before placing optional claim IDs or gate labels in parentheses. Assess which argument prevailed under the acceptance criteria, including when a narrower proposal or neither side prevailed. Distinguish this assessment from empirical validation and the user's final investment decision. Keep the full transcript and detailed tables in the accompanying report.

The moderator assesses the strength of the arguments but never assigns the user's scores, decides their investment verdict, or introduces new evidence.

## Moderator synthesis (after Turn 6 or optional Turn 8, before adjudication)

```markdown
## Debate Synthesis (Moderator)

**Proposal** · <one line> · **Horizon** · <horizon> · **Jurisdictions** · <list or "not supplied">
**Debate length** · <six or eight turns>
**Stopping decision** · <why six sufficed or the issue that justified the extra pair>

### Points of agreement
- <claim ID>. <what both agents accepted>

### Live disputes
- <P-xx vs D-yy>. <the disagreement in one sentence>. <what evidence would settle it>

### Evidence gaps ([UNK] items)
- <claim ID>. <the unknown>. <cost or effort to resolve>

### Concessions
- <claim ID>. <who conceded what>

### Unanswered cross-examination questions
- <claim ID and question>. <why it matters for the decision>

### Taste conflicts
- <where the user's stated taste conflicts with the evidence>. <the conflict in one sentence>
```

The moderator assesses the strength of the arguments but never assigns the user's scores, decides their investment verdict, or introduces new evidence.
