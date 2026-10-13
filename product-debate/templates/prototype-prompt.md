# Prototype Prompt Template

Generate this only when the user asks for a prototype handoff and V1 scope has settled. Load this file at that point. Never load it during the debate.

The prompt must be self-contained so the user can paste it into any AI prototyping or coding tool. It must match the final V1 exactly. Do not silently add features.

Follow the user-facing punctuation rules from `references/rules.md`. No em dashes, colons in prose, or semicolons.

## Required sections

```markdown
## Prototype. <name>

### Purpose
<one paragraph. What this is and what hypothesis it tests>

### Target user and triggering context
<who, what situation triggers use>

### Core job to be done
<one sentence>

### User's stated taste
<what the user thinks good looks like, or "none supplied">

### Primary user journey
<step by step>

### Required screens and interfaces
<list>

### Exact V1 capabilities
<list. Must match the V1 table exactly>

### Explicit non-goals
<list. Comes from the "Not in V1" section>

### Data model and state
<entities, fields, state transitions>

### Real vs. mocked integrations
<table. capability | real | mocked | why>

### Loading, empty, error, and recovery states
<for each screen>

### Privacy, safety, and accessibility requirements
<as applicable>

### Analytics events and properties
<event name | properties | why>

### Testable acceptance criteria
<numbered list>

### Hypothesis under test
<the specific falsifiable claim this prototype tests>

### Definition of success
<the outcome and evidence required for this prototype, not untested live-product claims>

### Usage and data requirements
<meaningful participation, event coverage, and data sufficiency needed to evaluate the hypothesis, or why these do not apply>
```

## Rules

- Use synthetic data by default. Do not request production credentials, real financial transactions, or unnecessary sensitive data.
- When the technical stack is unspecified, keep the prompt stack-neutral.
- Do not silently add features beyond the agreed V1.
- Do not simulate the very behavior or performance the experiment means to validate. When the hypothesis is "AI reduces delinquency," do not hard-code a fake delinquency reduction.
- Reflect the user's stated taste in the UI copy, tone, and quality bar when supplied.
