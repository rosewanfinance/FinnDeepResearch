# Skill: Bear Case / Devil's Advocate

## Purpose

Actively challenge the emerging investment thesis before it is finalized, so the conclusion is
adversarially validated rather than merely plausible.

## Inputs

- The current investment thesis.
- Supporting evidence and key assumptions (from all prior findings).
- The valuation and its most sensitive assumption (from `financial-valuation`).
- Identified risks.

## Questions this skill must ask

- What if the core assumption is wrong?
- What evidence contradicts the thesis?
- What could cause growth to disappoint?
- Which competitive threat is underestimated?
- What is *already priced in* to the valuation?
- Which assumption has the highest sensitivity?
- What observation would **invalidate** the thesis?

## Outputs

For each critical assumption, produce the challenge chain:

```text
Thesis
    ↓
Critical Assumption
    ↓
Counter Evidence
    ↓
Failure Scenario
    ↓
Potential Impact
    ↓
What Should Be Monitored
```

```yaml
bear_case:
  thesis: "..."
  challenges:
    - critical_assumption: "..."
      counter_evidence: "..."        # sourced, per evidence/claim schema
      failure_scenario: "..."        # concrete sequence of events
      potential_impact: "..."        # magnitude and direction
      monitor: "..."                 # observable indicator that would confirm this scenario
      likelihood: high | medium | low
      severity: high | medium | low
  most_important_risk: "..."         # the single biggest threat to the thesis
  invalidation_condition: "..."      # the observation that would overturn the thesis
```

## Constraints

- Be adversarial on the *thesis*, not hostile on the person.
- Every `counter_evidence` must be sourced; unbacked speculation is flagged as such.
- Do not invent a balanced-sounding bear case for its own sake — challenge only what actually
  matters.

## Reasoning mandate

Steelman the bear, then stress-test it the same way you stressed the bull. The output should make
it clear which risks are *priced* and which are *underappreciated* by the current valuation.

## Evidence requirements

- `counter_evidence` uses the evidence/claim schema (source, source type, date, confidence).
- `failure_scenario` must be a concrete sequence, not a generic "growth slows".

## Handoff format

Return the `bear_case` block. The Director feeds `most_important_risk` and
`invalidation_condition` into the final memo's risk and monitoring sections.

## Stopping conditions

Complete when:

- Every critical assumption has a challenge chain.
- The single most important risk is named.
- An explicit `invalidation_condition` (what would prove the thesis wrong) is defined.
