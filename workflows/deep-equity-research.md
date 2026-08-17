# Workflow: Deep Equity Research

> **This file defines *capabilities and schemas*, not a fixed sequence.**
> The Research Director ([`orchestration/director.md`](../orchestration/director.md)) decides the
> actual execution path each run. Treat everything below as "what may be combined and in what
> shape", not "what must happen in this order."

## Purpose

Turn a single, difficult investment question into a structured, evidence-backed research package
by composing reusable Skills under a Director's orchestration.

## Design principle

**Skills describe capabilities. The Director determines how those capabilities are composed.**

The available capabilities are:

| Capability | Skill file | Subagent |
|---|---|---|
| Research planning | [`skills/research-planning.md`](../skills/research-planning.md) | — (Director's job) |
| Fundamental research | [`skills/fundamental-research.md`](../skills/fundamental-research.md) | [`.claude/agents/fundamental-research.md`](../.claude/agents/fundamental-research.md) |
| Industry & competitive | [`skills/industry-competitive-research.md`](../skills/industry-competitive-research.md) | [`.claude/agents/industry-competitive-research.md`](../.claude/agents/industry-competitive-research.md) |
| Financial & valuation | [`skills/financial-valuation.md`](../skills/financial-valuation.md) | [`.claude/agents/financial-valuation.md`](../.claude/agents/financial-valuation.md) |
| Evidence & contradiction | [`skills/evidence-analysis.md`](../skills/evidence-analysis.md) | [`.claude/agents/evidence-analysis.md`](../.claude/agents/evidence-analysis.md) |
| Bear case / devil's advocate | [`skills/bear-case.md`](../skills/bear-case.md) | [`.claude/agents/bear-case.md`](../.claude/agents/bear-case.md) |

## How capabilities *may* compose

```text
Research Question
      |
      v
Decompose into sub-questions            (skills/research-planning.md, done by Director)
      |
      v
Assign skills to sub-questions
      |
      v
Parallel investigation                  (fundamental + industry + competitive + ...)
      |
      v
Evaluate evidence                       (skills/evidence-analysis.md)
      |
      +-- weak evidence ------> deeper research (recursive sub-question)
      |
      +-- contradictory ------> investigate the conflict
      |
      +-- sufficient --------> continue
      |
      v
Synthesize thesis
      |
      v
Challenge thesis                        (skills/bear-case.md)
      |
      v
Final research memo
```

This is a **loop with branches**, not a linear pipeline. The Director may revisit any step,
spawn recursive sub-questions, or stop a branch early (see "Stopping conditions" in
[`orchestration/director.md`](../orchestration/director.md)).

## Evidence-first model

Generated prose is never the primary research artifact. Findings move up a chain:

```text
Source  →  Observation  →  Claim  →  Interpretation  →  Investment Thesis
```

Every downstream step must be traceable back to a source. The Director locates weak arguments by
asking *where in this chain* the support breaks down.

## Shared schemas

These are the contracts between the Director and every Skill/subagent. All files reference them;
they are defined here once to avoid drift.

### 1. Research plan (`sub_questions`)

Produced by the Director using `skills/research-planning.md`.

```yaml
research_question: "..."              # original question, verbatim
decision_to_support: "..."            # the decision/answer the research should enable
investment_thesis_hypothesis: "..."   # candidate thesis, to be tested (may be rejected)
sub_questions:
  - id: <kebab-case>                  # stable identifier
    question: "..."                   # focused, answerable research question
    required_capabilities:            # from the capability table above
      - fundamentals
      - industry
    priority: high | medium | low
    dependencies: []                  # ids that should complete first
    required_evidence: "..."          # what evidence would settle this question
    quantitative: false               # needs numeric / valuation work?
    controversial_assumptions: []     # assumptions most likely to be wrong
```

### 2. Evidence / claim

Used by every Skill to attach provenance to assertions.

```yaml
claims:
  - claim: "..."                      # one checkable assertion
    source: "..."                     # filing / report / URL / transcript
    source_type: filing | earnings_call | management | sell_side | buy_side | news | primary_data | third_party
    publication_date: "YYYY-MM-DD"
    supporting_evidence: "..."        # the specific observation backing the claim
    confidence: high | medium | low
    flags: []                         # unsupported | weak_source | outdated | management_only | overreach
    contradicts: <claim-id> | null
```

### 3. Research finding (subagent handoff envelope)

Every research subagent returns this shape so the Director can evaluate it mechanically.

```yaml
finding:
  question_id: <kebab-case>           # matches the plan
  question: "..."
  capability: <fundamentals | industry_competitive | financial_valuation>
  answer: "..."                       # 1-3 sentence direct answer
  growth_attribution: "..."           # industry/competitive only: market growth vs share gain vs both
  key_claims: []                      # entries from the evidence/claim schema
  key_assumptions:                    # assumptions made, with provenance
    - { assumption: "...", origin: historical | industry_forecast | company_guidance | analyst | inferred, confidence: high | medium | low }
  quantitative_results: []            # financial/valuation only: figures + assumption origins
  open_questions: []                  # what remains unresolved
  confidence: high | medium | low     # overall confidence in this finding
  sources: []                         # canonical source list
```

## Breadth vs. depth

Two dimensions are optimized independently (§9 of the proposal):

- **Breadth** — cover independent dimensions in parallel: company, industry, competition,
  customers, suppliers, financials, macro, technology, regulation, valuation.
- **Depth** — when an important uncertainty is discovered, recurse into it rather than accepting a
  surface answer.

The goal is **parallel exploration + evidence evaluation + recursive investigation + adversarial
validation** — not "parallel search."

## Benchmark question

See [`examples/nvidia-ai-infrastructure/question.md`](../examples/nvidia-ai-infrastructure/question.md):

> Is NVIDIA's current valuation justified by the expected growth of AI infrastructure spending over
> the next three years?

This question exercises every capability, which is why it is the primary demonstration.
