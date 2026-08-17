# Skill: Research Planning

## Purpose

Convert a broad investment question into a structured, executable research plan. This is the
Director's first job (see [`orchestration/director.md`](../orchestration/director.md)) — it is a
methodology the Director applies, not a separate delegated task.

## Inputs

- The original research question (verbatim).
- The decision the research should support (if stated by the user; otherwise inferred and stated
  explicitly as an assumption).

## Outputs

A structured plan following the `sub_questions` schema defined in
[`workflows/deep-equity-research.md`](../workflows/deep-equity-research.md#1-research-plan-sub_questions).

```yaml
research_question: "..."
decision_to_support: "..."
investment_thesis_hypothesis: "..."
sub_questions:
  - id: revenue_growth
    question: "..."
    required_capabilities: [fundamentals, industry]
    priority: high
    dependencies: []
    required_evidence: "..."
    quantitative: false
    controversial_assumptions: ["..."]
```

## Responsibilities

1. Identify the **main investment thesis** implied by the question (an explicit hypothesis to be
   tested, not assumed true).
2. **Decompose** the thesis into focused sub-questions that are individually answerable.
3. Identify **dependencies** (which sub-questions must be answered before others).
4. Identify the **evidence required** to settle each sub-question.
5. Assign the **relevant capabilities** (fundamentals, industry, valuation, etc.).
6. Flag sub-questions that require **quantitative analysis**.
7. Flag **controversial assumptions** — the claims most likely to be wrong and most worth a deep
   dive or bear-case challenge.

## Constraints

- Prefer a small number of high-value sub-questions (typically 6–10) over a long shallow list.
- Every sub-question must map to at least one capability; if none fits, the question is out of
  scope for this prototype.
- `priority` reflects importance to the *thesis*, not curiosity.
- Do not pre-answer sub-questions in the plan; the plan schedules investigation, it does not
  perform it.

## Reasoning mandate

Think like a research lead scoping a desk's work: what, if answered with evidence, would change
the conclusion? Decompose along the dimensions in the proposal (growth, industry, competition,
financials, valuation, catalysts, risks). Each sub-question should have a falsifiable answer.

## Evidence requirements

For each sub-question, state `required_evidence` concretely enough that a subagent can tell when it
is satisfied (e.g. "segment-level revenue trend over 8 quarters" rather than "more data").

## Handoff format

This skill's output is consumed by the Director only, in the `sub_questions` schema above. It is
not returned by a subagent.

## Stopping conditions

Planning is complete when:

- The main thesis is explicit and testable.
- Sub-questions are mutually non-redundant and jointly cover the thesis.
- Dependencies and capabilities are assigned.
- Controversial assumptions are named (so the bear case and evidence analysis know what to target).
