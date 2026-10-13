# Adjudication Rubric (for the user)

The user scores the proposal on six dimensions. Higher always favors the proposal, including on the risk dimensions. A 5 on Regulatory means clean or low exposure, not high risk.

## Weights

| # | Dimension | Weight | The question |
|---|---|---|---|
| 1 | Market and customer value | 20% | Will the target customer demonstrably switch from the stated alternative? |
| 2 | Monetization | 20% | Does the pricing logic survive contact with willingness-to-pay evidence? |
| 3 | Distribution and virality | 10% | Is there a credible acquisition path at tolerable CAC? |
| 4 | Unit economics | 20% | Does contribution margin pay back CAC within the horizon? |
| 5 | Retention and churn | 15% | Do the cohort math and repeat-demand story hold? |
| 6 | Regulatory and compliance | 15% | Is the operating model permissible in the stated jurisdictions? |

**Virality handling.** When virality is irrelevant to the proposal (the Proponent said so plainly and the Devil's Advocate did not dispute it), assess the 10% Distribution dimension using the non-viral acquisition path instead. Do not penalize the product for lacking a viral loop. Do not redistribute the weight. Distribution still matters.

**Taste handling.** The user may score any dimension against their stated taste when the evidence is inconclusive. Note the taste basis in the scorecard. Taste does not override the hard gates or the Unknown-confidence rules.

## Anchored 1–5 scale (per dimension)

Each dimension has its own outcome anchors for 1, 3, and 5. Interpolate scores 2 and 4 between them. The anchors below are examples. The moderator fills in the user's stated requirements where the charter supplies them.

| Dimension | Score 1 | Score 3 | Score 5 |
|---|---|---|---|
| Market and customer value | No demonstrable reason for the target customer to switch from the stated alternative | The switching case is plausible but unproven. The outcome depends on unvalidated assumptions. | Bottom-up evidence or strong analogues shows the customer switches and gets the job done better. |
| Monetization | Willingness-to-pay evidence contradicts the pricing model | Pricing is plausible. Willingness to pay is assumed, not evidenced. | Willingness-to-pay evidence or close analogues supports the model, including expansion revenue. |
| Distribution and virality | No credible acquisition path at tolerable CAC | A path exists on paper. CAC is an estimate, not a measurement. | A measured or closely analogous channel shows tolerable CAC. The viral loop is present and evidenced, or the non-viral path is measured. |
| Unit economics | Contribution economics or payback fail the user's stated requirements | Base-case economics meet requirements but are sensitive to adverse assumptions. | Base and downside cases both meet the agreed requirements. |
| Retention and churn | Cohort math shows the product cannot retain customers past early adopters | Retention is plausible but rests on assumed cohort behavior. | Cohort evidence or close analogues supports durable retention at the assumed scale. |
| Regulatory and compliance | A confirmed prohibition or licensing bar in a stated jurisdiction | Material unresolved exposure. Authoritative material is not yet reviewed. | Authoritative material or qualified review confirms permissibility in every stated jurisdiction. |

## Evidence confidence (tracked separately, per dimension)

`High` — mostly `[FACT-V]` · `Medium` — a mix of facts and `[ASSUME]`/`[EST]` · `Low` — mostly `[ASSUME]` · `Unknown` — dominated by `[UNK]`

**Confidence rules**

1. An `Unknown` dimension scores a provisional 3. The placeholder means "not established," not a real assessment of the proposal. The scorecard marks it `3*`.
2. **No full Proceed while any decision-critical dimension (weight ≥ 15%) remains `Unknown`.** A 4.60 weighted score with a 20%-weight dimension at `3*` caps the verdict at Pilot, not Proceed.
3. **Pilot is available only when a bounded, permissible experiment can actually resolve the material uncertainty.** When the unknown cannot be resolved by a pilot (it requires regulatory review or market-scale data), the verdict is Hold for Evidence.
4. Agreement between the agents does not establish truth. Both may rely on the same unvalidated assumption.
5. User taste does not substitute for evidence on a decision-critical dimension. Taste can raise or lower a score within the evidence bounds, but it cannot convert an `Unknown` into an established result.

## Hard gates (evaluated before the weighted score)

| Gate | Question | Fail means |
|---|---|---|
| **G1 Legality** | Is the operating model permissible in every stated jurisdiction? | Do-not-proceed path, regardless of score |
| **G2 Dependency feasibility** | Does every load-bearing dependency (API, partner, license, platform) actually exist on acceptable terms? | Do-not-proceed or reframe |
| **G3 Data and consent rights** | Can the product lawfully obtain and use the data it needs? | Do-not-proceed or reframe |

- A **confirmed** gate failure (established by authoritative material or qualified review, not by a hypothesized mechanism) caps the verdict at Do not proceed or reframe.
- A gate with **material uncertainty** caps the verdict at Hold for evidence. It cannot be averaged into a Proceed.
- Gates are checked against `[FACT-V]` evidence or qualified review. A gate cannot fail on the Devil's Advocate's speculation alone. It cannot pass on the Proponent's assumption or the user's bare assertion alone.
- User taste cannot open or close a gate.

## Calculation

```
Weighted score = Σ (dimension score × weight)   → 1.00 to 5.00
```

## Verdict bands (gates pass, no decision-critical `Unknown`)

| Weighted score | Default verdict |
|---|---|
| S ≥ 4.0 | **Proceed** |
| 3.0 ≤ S < 4.0 | **Proceed with conditions. Run a pilot.** |
| 2.0 ≤ S < 3.0 | **Hold for evidence** |
| S < 2.0 | **Do not proceed. Reframe.** |

The bands are defaults, not overrides. The user may always render a stricter verdict. The template requires the rationale either way.
