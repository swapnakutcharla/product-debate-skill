# /ProductDebate User Guide

This skill turns a product idea into a decision. It runs six turns between two simulated agents, with one optional matched exchange bringing the total to eight. It defines the minimum V1, builds a validation plan, and hands you a scorecard and verdict template. You retain the final decision.

## Why this exists

Most product decisions fail in one of two ways.

1. **Too much enthusiasm.** Everyone loves the idea. Nobody asks the uncomfortable question. You build something nobody needed.
2. **Too much caution.** Every risk feels fatal. Nothing ships. You learn nothing.

`/ProductDebate` forces the productive middle. Two agents argue opposing cases under strict rules. The friction between them produces what a single perspective cannot. It surfaces the specific reasons this might fail and the cheapest experiment that would settle the question.

You are the judge. The agents never decide. You do. The readout gives you the decision-ready summary first. The full detail stays one command away.

---

## What one run delivers

| Deliverable | What it does for you |
|---|---|
| **Quick recap** | The idea, the work completed, and the material working assumptions |
| **Plain-English debate synthesis** | Strongest arguments for and against, which side or revised idea prevailed, and what remains unproven |
| **Hidden assumptions and tests** | The most consequential assumptions in a compact table. What breaks if false, cheapest resolving test, decision rule |
| **Minimum V1 and exclusions** | The smallest coherent experiment and what stays out. Distinguishes a synthetic prototype from a real-customer pilot |
| **Production requirements** | What must be true before launch, why it matters, and what evidence clears each requirement |
| **Success metrics and tradeoffs** | The north-star customer outcome, business value, safety guardrails, and choices to make deliberately |
| **Definition of success** | What outcome and evidence would justify advancing at the current stage, including meaningful usage and data sufficiency when relevant |
| **High-level success and launch plan** | What must be true, the work and tests that establish it, and the criteria for moving from discovery to pilot and launch |
| **Validation recommendation** | A sequenced plan linked to success and launch requirements, plus one concrete first action |
| **Full report** | Complete objection ledger, metrics, guardrails, rubric, scorecard, actual six- or eight-turn transcript, and stopping decision in a downloadable file |
| **Optional prototype prompt** | A self-contained, stack-neutral prompt for an AI prototyping tool. Only when you ask for it. Only after V1 scope settles. |

---

## The output structure

The default response explains the meaning before any internal code. You do not need to know the rubric to understand the recommendation.

1. **Quick recap.** What the skill tested and how.
2. **Debate synthesis.** The strongest arguments for and against and which argument prevailed.
3. **Hidden assumptions and tests.** The compact table.
4. **V1 proposal and minimum features.** The smallest coherent experiment and what would satisfy the skeptic's justified requirements for a test.
5. **What must be true before production.** Launch requirements, evidence needed, and affected stages.
6. **Success metrics, guardrails, and tradeoffs.** Separate subsections define success, translate it into outcome, usage, business, and data-sufficiency metrics, and explain deliberate choices.
7. **How to validate and move forward.** A high-level plan links the requirements to resolving tests, product or operating work, pilot and launch criteria, and a concrete first action.

The skill explains which argument prevailed, not which product has been validated. A narrower idea may prevail even when the original scope does not. You still own the final verdict and scorecard.

The full six- or eight-turn transcript, stopping decision, objection ledger, detailed metrics, guardrails, rubric, and scorecard go into a downloadable report file.

### Showing and hiding the transcript

Two commands control the transcript.

- **"Show full debate"** shows the retained six- or eight-turn transcript in the next response.
- **"Return to summary"** returns to the readout structure in the next response.

These commands change subsequent responses. They do not remove earlier chat messages. The skill retrieves the retained transcript rather than regenerating a different debate.

---

## How to invoke it

Plain language works.

- `/ProductDebate <your idea in one paragraph>`
- "Run a product debate on this idea"
- "Red-team this before we commit to building it"
- "Should we proceed with X?"

The more context you supply, the sharper the debate. At minimum include **what you build, who it serves, and what they use today instead.**

### A short intake before the debate

The skill asks for missing information in one message before starting. It asks what principles or product taste should shape the idea, which core hypotheses you want tested, and what supporting or contradictory evidence you have gathered.

You can say "no preferences," "help me frame the hypotheses," or "no evidence yet." You can also ask to skip intake and proceed with labeled assumptions. The skill does not repeat questions already answered or request the same intake again for an unchanged rerun.

Supply these upfront to avoid an extra exchange.

```markdown
Product idea and target customer
<Your idea and initial segment>

Guiding principles or product taste
<What good looks like and any non-negotiable boundaries>

Core hypotheses to test
<The causal, adoption, customer, or business claims and possible falsifiers>

Evidence gathered
<Supporting and contradictory evidence, or no evidence yet>

Launch jurisdiction
<Optional. Defaults to the United States.>
```

When you omit the jurisdiction, the skill assumes a US launch and states the assumption. Applicable state rules, product scope, and deployment permissions still require review. A default is not legal approval.

### Concise by default

Routine runs use six turns, targeted verification, and a compact report. The seven-section readout and full retained transcript remain available.

Ask for a deeper run when you need expanded research or longer arguments. The skill does not promise an elapsed time. Intake wait time and execution time are separate.

### Six turns, with a purposeful extension

| Turns | Job |
|---|---|
| 1 and 2 | Present the strongest case and challenge it with explicit acceptance criteria |
| 3 and 4 | Revise the hypothesis and minimum V1, then test whether the revision addresses the objections |
| 5 and 6 | Resolve the highest-impact question, propose the experiment, and state conditional acceptance or rejection |
| Optional 7 and 8 | Address a consequential unresolved objection through one targeted revision and challenge |

The moderator checks after Turn 6 whether more reasoning could change the hypothesis, V1, acceptance criteria, safety controls, or next validation test. If those are stable and the remaining gaps need customer evidence, private data, or qualified review, it stops.

It adds the pair only when a consequential objection remains unanswered and further reasoning could matter, or when you explicitly request eight turns. It records the reason and never exceeds eight. There are no separate closing speeches or unanswered questions carried beyond the final turn.

Ask for "six turns only" to prohibit the extension, or "use eight turns" to request the extra pair. Asking for deeper research changes depth, not automatically the turn count. Eight means eight total turns, not eight additional turns.

---

## The taste field

Tell the skill what you think good looks like. Your product instincts, your non-negotiables, your quality bar, what you refuse to build. The skill calls this **taste**.

Taste works three ways.

1. **The Proponent uses it** to sharpen positioning and the V1.
2. **The Devil's Advocate uses it** to spot conflicts between your instincts and the evidence.
3. **The synthesis surfaces those conflicts** so you decide, rather than the debate silently resolving them.

Preferences are inputs the agents can challenge. Explicit non-negotiable boundaries become constraints the design must honor or openly flag as incompatible. Neither preferences nor constraints establish evidence, clear a legal requirement, or convert an Unknown into a result.

Supply it like this. "Taste. I want this to feel calm and protective, never salesy. I refuse to build anything that nudges a customer away from filing a dispute. Fast resolution matters more than cost savings."

---

## Best practices

### Supply the awkward facts up front

The Devil's Advocate is only as strong as the numbers you hand it. When you have data that weakens your case (low conversion, churn you are embarrassed by, a competitor you fear), supply it. The debate is more useful when the skeptic gets to use your own evidence against you.

### State your taste

Your instincts are data. When you share what good looks like, the debate tests your idea against your standard, not a generic one. When your taste conflicts with the evidence, the synthesis names the conflict. That is often the most valuable output of the whole run.

### Do not score while the debate runs

Score the proposal, not the agents' rhetorical performance. An eloquent Proponent is not a validated business. A thorough Devil's Advocate is not a dead idea. Wait for the scorecard. Then judge the proposal on the six dimensions.

### Treat "Unknown" as a real answer

When a decision-critical dimension (weight ≥ 15%) comes back `Unknown`, the skill blocks a full Proceed on purpose. Do not fight it. It protects you. The right next step is the evidence backlog, not another debate.

### Hard gates cannot be averaged away

Three gates (legality, dependency feasibility, data rights) are checked before the weighted score. A confirmed failure caps the verdict at Do-not-proceed regardless of how good the other numbers look. When a gate is uncertain, the verdict is Hold, not Pilot.

### Read the "Not in V1" section first

The exclusions tell you what the debate decided you do not need yet. Scope creep in early-stage products usually starts by re-adding things the removal test already killed.

### Run the cheapest disqualifying test first

The validation plan sequences tests deliberately. The $5k thing that can kill the idea runs before the $500k thing that only confirms it. Resist the temptation to start with the expensive, exciting test.

### Do not call it validated when it has only been argued

The skill enforces this. "Answered in argument" means rebutted logically, not tested. When a critical assumption is still `[ASSUME]` or `[UNK]`, it is not a fact. It is the next experiment.

### Use the prototype prompt as a handoff, not a substitute for thinking

The prototype prompt is generated only after V1 scope settles and must match it exactly. It bridges to an AI prototyping tool. It is not a decision in itself.

---

## What the skill will not do

- **It will not decide your investment verdict.** The moderator explains which argument prevailed and why. You adjudicate whether to build, test, revise, or stop.
- **It will not resolve legal or compliance questions.** A debate does not grant legal, security, or compliance approval. Items requiring qualified review get flagged, not answered.
- **It will not invent facts or citations.** `[FACT-V]` requires a real source. Unverifiable claims get tagged `[ASSUME]`, `[EST]`, or `[UNK]`.
- **It will not treat winning a debate as product-market fit.** Persuasion is not validation.
- **It will not let taste override evidence.** Taste shapes scores within the evidence bounds. It cannot open or close gates or convert Unknowns into facts.

---

## Common failure modes (and how to avoid them)

| Symptom | Cause | Fix |
|---|---|---|
| Debate feels like theater, no real disagreement | Intake was too thin. Agents had nothing concrete to fight over. | Supply more specifics. Numbers, competitors, customer quotes, current metrics. |
| Devil's Advocate sounds like a cynic, objecting to everything | The role prompt says "do not oppose for sport." When your idea has no real risk surface, the DA has nothing to work with. | Check whether the idea is actually early. When it is already validated, you may not need a debate. |
| V1 keeps growing | The removal test is not being applied honestly. | Re-run it. "When this is removed, can we still deliver and evaluate the core outcome safely?" |
| You want to Proceed but the gates say Hold | A hard gate is materially uncertain. | Do not override it. Run the resolving evidence first. That is exactly what the Hold template's evidence-unlock table is for. |
| Metrics do not match the claim | Denominator mismatch. "47% late" vs. "47% 30+ day delinquent." | Check the metric definition in the validation package. Denominator, source, window, baseline. |
| Agents agree on something that is still just an assumption | Agreement is not truth. Both may rely on the same unvalidated input. | Look for the `[ASSUME]` tag in the agreement. That is the next test. |
| Your taste and the evidence point in different directions | You supplied taste and the debate surfaced a conflict. | Read the taste-conflict section in the synthesis. Decide explicitly. Do not let the debate silently resolve it. |

---

## Quick reference

**Six dimensions, weighted**

| Dimension | Weight |
|---|---|
| Market and customer value | 20% |
| Monetization | 20% |
| Distribution and virality | 10% |
| Unit economics | 20% |
| Retention and churn | 15% |
| Regulatory and compliance | 15% |

**Three hard gates, checked before the score.** Legality, dependency feasibility, data and consent rights.

**Verdict bands.** ≥ 4.0 Proceed · 3.0 to 3.9 Pilot · 2.0 to 2.9 Hold · < 2.0 Do-not-proceed or reframe.

**Evidence tags.** `[FACT-S]` supplied · `[FACT-V]` verified with source · `[ASSUME]` falsifiable assumption · `[EST]` estimate with arithmetic · `[UNK]` unknown with resolving evidence named.

**Claim IDs.** Proponent `P-01, P-02, …` · Devil's Advocate `D-01, D-02, …` · Objections `O-01, O-02, …` · Unknowns `U-01, U-02, …`

**Intake.** The skill asks for missing principles or taste, core hypotheses, and gathered evidence in one message. Answers can be brief or explicitly absent.

**Taste.** Supply what good looks like in your own words. The debate engages with it. You adjudicate the conflicts.

**Launch market.** The United States is the declared default unless you specify another jurisdiction.

---

## How to install it

The skill lives in the `product-debate/` folder of this repository. You can install it two ways.

**In the Claude app.** Open the Releases section on the right side of this page and download `product-debate.zip` from the latest release. Then upload that zip under Skills in Claude's settings. The skill loads whenever you ask for a structured product debate, a red team product review, or a proceed versus hold decision.

**In Claude Code.** Clone this repository and copy the `product-debate/` folder into `~/.claude/skills/` for personal use, or into `.claude/skills/` inside a project to share it with that project's team.

## License

The package uses the MIT license. You can use, modify, and redistribute it, including commercially, while retaining the copyright and permission notice. Read the bundled `LICENSE` file for the complete terms and warranty disclaimer.
