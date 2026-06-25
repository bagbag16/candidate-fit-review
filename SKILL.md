---
name: candidate-fit-review
description: "Analyze whether a candidate design, rule, workflow, process, or mechanism A should be introduced into a target system, process, or framework B. Use when the task is to judge necessity-first fit and net value rather than to implement immediately, including when the user refers to this skill as candidate-fit-review or cfr: compare real problems, current coverage, benefits, costs, Occam necessity, simpler alternatives, and the minimum atomic integration point; then recommend not absorbing, keeping as reference, piloting, formally absorbing, or replacing an existing mechanism."
---

# Candidate Fit Review

Analyze whether candidate A should enter target B.

Keep the skill independent. Do not assume B uses any particular framework, state model, or terminology unless the user provides it. Do not import concepts from unrelated skills or systems into the analysis.

## Core Principles

Apply these as hard constraints:

- Prioritize truth over completeness. Analyze only real A, real B, and real problems.
- Prioritize support over fluency. Do not state conclusions more strongly than the evidence allows.
- Require value. Reject candidates whose main benefit is only looking richer, newer, or more complete.
- Start with necessity. Identify the concrete failure B needs to prevent before judging whether A is attractive.
- Require necessity. Prefer improving an existing mechanism when the problem is execution quality rather than a missing rule or capability.
- Apply Occam's razor as a necessity gate, not a small-change rule. Add the entity that is needed, remove or merge the entity that is not needed, and reject entities that only make B look more complete.
- Apply minimum atomization. If A is worth introducing, recommend the smallest independently evaluable, governable, and reversible unit rather than importing A wholesale.

## Occam Necessity Gate

Run this gate before recommending absorption.

The first question is not "is A good?" or "is A smaller?" The first question is "what makes a change necessary for B?"

Occam's razor in this skill means: use the fewest unnecessary entities while still solving the real problem. Do not prefer a smaller change if it hides complexity, weakens coverage, or pushes ambiguity into future judgment.

Ask:

- What concrete failure does A prevent?
- Is that failure real, recurring, high-impact, or likely enough to justify formal handling?
- What breaks or becomes harder if A is not introduced?
- Can an existing mechanism cover the same failure without becoming ambiguous or overloaded?
- Does A answer a distinct decision, or repeat another entity?
- Would merging A into an existing mechanism make execution clearer or harder?
- Is A needed now, or only anticipated as a possible future need?

High-frequency constraints:

- Add only when there is a named failure, trigger, and owner or reader.
- Merge or replace when two entities answer the same decision.
- Keep as reference when A is useful background but not necessary state or procedure.
- Reject when A mostly adds completeness, vocabulary, optional flexibility, or speculative future coverage.
- Count hidden complexity: explanation burden, maintenance burden, future conflict risk, and memory burden are still costs.
- Do not remove an existing entity until its purpose and downstream dependents are understood.

Use these related principle cores:

- YAGNI: do not absorb speculative future capability before there is actual demand.
- Chesterton's Fence: do not remove or replace an existing entity before understanding why it exists and what depends on it.
- KISS: prefer the clearest effective mechanism, not the shortest textual change or smallest patch.
- DRY / single source of truth: one decision should have one authoritative representation; duplicate knowledge should be merged, generated, or replaced.
- Lean waste: treat untriggered, unowned, unused, redundant, or purely decorative entities as waste unless they add real value.

## Use Rules

Use this skill only when the task is about whether something should enter B.

Good fits:
- deciding whether to absorb an external design into an existing system
- reviewing whether a new rule or workflow is necessary
- comparing a candidate mechanism against current coverage
- determining whether to keep something as reference, run a pilot, or formally adopt it

Do not use this skill for:
- immediate implementation work
- open-ended brainstorming without a concrete A and B
- abstract philosophy detached from a target object
- tasks where the user only wants a description, summary, or rewrite

If A, B, or the actual problem is unclear, say so and lower the conclusion strength. Do not silently fill in missing definitions.

## Required Inputs

Gather as much of this as possible before concluding:

- what A actually is
- what B actually is
- what problem B is currently facing
- what current mechanisms B already has in the relevant area
- known failure modes, costs, or limits in B today
- available evidence, examples, or readback material that supports comparison

If the input is incomplete, continue only as far as the evidence allows and explicitly mark the missing pieces.

## Analysis Workflow

Work in this order:

0. Run the necessity-first gate.
Before comparing solutions, identify why B needs any change at all. If there is no concrete failure, recurring risk, or high-impact decision that A would improve, recommend `do not absorb` or `reference only`.

1. Define the current problem.
Identify the real pain point inside B. Do not begin by praising or summarizing A.

2. Define what A actually adds.
Describe the mechanism, constraint, workflow, or capability A introduces. Strip away marketing language.

3. Check B's current coverage.
Judge whether B already covers the problem fully, partially, only superficially, or not at all.

4. Classify the gap.
Distinguish at least:
- rule gap
- execution gap
- tool gap
- information gap or unclear diagnosis

Do not recommend a new mechanism if the issue is only weak execution of an existing one.

5. Evaluate net benefits.
Count only real gains such as improved stability, traceability, recoverability, maintainability, or lower invocation cost.

6. Evaluate costs and risks.
Always assess:
- complexity cost
- coupling cost
- maintenance cost
- misuse risk
- rollback cost

7. Search for simpler alternatives.
Ask whether a smaller or lighter change could achieve most of the same benefit. Do not equate smaller with better if it would leave the real failure unresolved or move complexity into implicit judgment.

8. Find the minimum atomic integration point.
If A is worth introducing, identify the smallest concept, rule, process, or module that should enter B.

9. Choose a recommendation.
Allowed outcomes:
- `do not absorb`
- `reference only`
- `pilot locally`
- `absorb formally`
- `replace an existing mechanism`

10. Mark open questions.
List unresolved premises that prevent a stronger conclusion.

## Output Shape

Default to this structure:

```md
# Fit Review

## Necessity Gate
## Current Problem
## What A Adds
## Current Coverage in B
## Gap Type
## Net Benefits
## Costs and Risks
## Simpler Alternatives
## Minimum Atomic Integration Point
## Recommendation
## Open Questions
```

Keep each section substantive. Do not add sections just to look complete.

## Self-Check

Before finalizing, check:

- Are A, B, and the problem real and clearly bounded?
- Did the analysis start from necessity rather than attractiveness, completeness, or novelty?
- Did every proposed new entity name the failure it prevents?
- Did speculative future value get rejected, deferred, or kept as reference instead of absorbed?
- Did the analysis identify the purpose and dependents of any existing entity before removing or replacing it?
- Did it preserve one authoritative representation for each decision or piece of knowledge?
- Did it reject entities that do not add real value to B?
- Did the analysis avoid treating a smaller change as automatically better?
- Did it merge, replace, reject, or keep as reference any overlapping entity instead of stacking duplicates?
- Does each important claim have support?
- Did the conclusion strength stay aligned with the evidence strength?
- Did the analysis distinguish a missing rule from weak execution?
- Did the analysis compare benefits against real costs?
- Did the analysis look for a simpler path before recommending absorption?
- Did the recommendation identify the smallest viable integration point?
- Did the output avoid turning a suggestion into a decision?

If any answer is no, weaken the conclusion or surface the missing support instead of forcing a stronger answer.
