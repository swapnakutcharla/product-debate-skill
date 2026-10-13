# Objection Ledger and Validation Package

Produce these after the six-turn debate or optional eight-turn debate, before the user-facing scorecard. The moderator owns these outputs, not either agent.

Follow the user-facing punctuation rules from `references/rules.md`. No em dashes, colons in prose, or semicolons.

## Objection ledger

Track every material objection raised during the debate.

| Field | Description |
|---|---|
| ID | `O-01, O-02, …` |
| Objection | One sentence |
| Consequence if true | One sentence |
| Supporting claim | Claim ID plus evidence tag |
| What would resolve it | One sentence |
| Resolution type | See the taxonomy below |
| Status | `answered-in-argument`, `requires-testing`, or `unresolved` |
| Blocks | `synthetic-prototype`, `customer-pilot`, `production-launch`, or `none` |

**Resolution-type taxonomy**

| Type | Meaning | Default remedy |
|---|---|---|
| `A. Feature` | Requires a product capability | Build it |
| `B. Evidence` | Requires customer or market data | Test it |
| `C. Positioning` | Requires a narrower segment or scope | Rescope it |
| `D. Operational` | Requires a policy or operational control | Operationalize it |
| `E. Strategic` | Potentially fatal to the core hypothesis | Do not paper over it |

**Rules**

- "Answered in argument" is not empirical validation. It means the objection was rebutted logically. The underlying assumption may still be untested.
- Do not convert types B, C, D, or E into a feature by default.
- The ledger is separate from, and does not replace, the hard gates. Gates identify blockers. The ledger explains how each objection is remedied.

## Minimum V1 extraction

After the ledger, derive the smallest coherent V1 that can test the most consequential remaining hypothesis. The target is not "the smallest list that makes the Devil's Advocate verbally agree." It is the smallest testable product that meets the DA's justified requirements for a bounded experiment.

**Inclusion test. A capability belongs in V1 only when it is necessary to do one of the following**

1. Deliver the core customer outcome.
2. Test a critical assumption.
3. Measure the outcome.
4. Satisfy a non-negotiable safety or operating constraint.

**Removal test. For each proposed capability, ask**

> "When this is removed, can we still deliver and evaluate the core outcome safely?"
> When yes, exclude it from V1.

Present the V1 in three tables.

```markdown
### Customer-facing capabilities
| Capability | Customer outcome enabled | Objection or assumption addressed | Why it is required now | Smallest acceptable implementation | Measurement required |

### Instrumentation
| Capability | What it measures | Why it is required now |

### Operational controls
| Capability | What it guards against | Why it is required now |
```

**Additional rules**

- Prefer manual, concierge, or simulated operations where appropriate. Label them clearly. Do not simulate the very behavior or performance the experiment means to validate.
- When no coherent V1 survives the removal tests, say so. Recommend the smallest useful research or feasibility test instead of manufacturing a feature set.
- List explicit exclusions. State what is **not** in V1 and why it can wait.
- When the user supplied taste, test the V1 against it. Flag any capability the user's taste rules out that the evidence supports, and any capability the user's taste requires that the evidence does not.

## Validation plan (evidence backlog)

For each critical assumption in the ledger, specify the following.

| Field | Description |
|---|---|
| Assumption | Claim ID plus one sentence |
| Test | What you would do |
| Target segment | Who, specifically |
| Observable behavior | What you would watch |
| Decision rule | Threshold and what it implies |
| Limitation | Known confounders |

**Sequencing rule.** Run cheap, potentially disqualifying tests before expensive development. When a $5k legal review can kill the idea, run it before a $500k build.

## Definition of success

State what would count as success for the current stage, not merely which indicators to track. Connect it to the user's core hypotheses and guiding principles.

- Specify the intended customer outcome, the population, comparator, observation window, and the evidence that would justify advancing.
- Define sufficient real usage and suitable data to evaluate that outcome when relevant. Explain whether active participants, eligible episodes, completed journeys, outcome-labeled records, coverage, or rare-risk observations matter.
- Separate product success from evidence sufficiency. A large dataset or high usage is not success if the customer outcome fails or safety deteriorates.
- Use user-supplied targets when supported. Otherwise offer a provisional target with rationale or state how the target will be set. Do not invent a universal minimum user count or data-volume quota.
- Distinguish synthetic prototype, pilot, and production success. Mock transactions cannot establish real repayment, fraud prevention, or live execution.

## High-level plan for achieving success

Link the two parts rather than repeat disconnected lists.

1. **What must be true.** Name customer, evidence, usage or data sufficiency, dependency, operational, economic, and launch conditions that matter. Show why each matters and its status.
2. **How to establish it and launch.** Map each condition to its cheapest resolving test, necessary V1 or operating work, advancement criterion, and the next stage. Sequence discovery, feasibility, prototype, approved pilot, and launch only where applicable.

| What must be true | Test or work that establishes it | Evidence or acceptance criterion | Dependency and stage | Accountable role |
|---|---|---|---|---|
| <Condition> | <Test, implementation, or approval> | <Result that changes the plan> | <Prerequisite and stage> | <Suggested role, not an invented assignee> |

End with the first concrete action, the evidence it will produce, and a conditional advance, revise, or stop rule. Do not promise launch dates or budgets without supplied inputs.

## Success metrics

Translate the definition of success into measurable indicators rather than restating the desired outcome. Include one north-star outcome, business value, meaningful usage, data sufficiency when required, and material safety measures. Explain when usage or data volume is not relevant instead of forcing vanity counts.

For each metric, define the following.

- **Definition and denominator.** For example, "30+ day delinquency rate among contacted at-risk borrowers, not all active borrowers."
- **Measurement event or source.** Where the data comes from.
- **Observation window.** How long you measure.
- **Baseline.** State it when known. Otherwise mark "no baseline."
- **Proposed threshold.** State whether it is `measured` or `provisional`. Provisional thresholds must carry their rationale.
- **Action.** What you do when the threshold is met or missed.
- **Evidence sufficiency.** Whether data are complete, representative, mature enough, and statistically suitable for the decision. Report selection bias, missing outcomes, and important rare-event limits.

**Quality checks**

- Distinguish "any late payment" from "30+ day delinquency." These are different denominators.
- Distinguish "reduction among contacted borrowers" from "relative delinquency reduction across the book." These use different arithmetic.
- Avoid vanity metrics that do not test the hypothesis.

## Guardrails and stop conditions

Separate by stage.

```markdown
### Prototype restrictions
### Pilot controls
### Requirements before production launch
```

For each guardrail, specify the constraint, why it exists, and what happens when it is violated (stop condition plus response).

Include, as applicable, privacy and data handling, safety and misuse, reliability and failure recovery, financial exposure, customer support burden, accessibility, and legal or compliance questions that require qualified review.

**Rules**

- An unresolved legal question may block a real-customer pilot without blocking a synthetic-data prototype. Gate by stage.
- Calling something a "pilot" does not waive a regulatory or data-rights gate.
- A product debate is not legal, security, or compliance approval. Flag items that require qualified review. Do not resolve them in the debate.
- When the user supplied taste, include a taste-conflict section. List where the user's instincts conflict with the evidence and what the user should decide.
