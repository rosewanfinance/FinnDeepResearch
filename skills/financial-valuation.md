# Skill: Financial & Valuation Analysis

## Purpose

Translate research findings into quantitative financial implications, and assess whether the
current valuation is defensible under bull/base/bear scenarios.

## Inputs

- A `sub_question` from the research plan (with `required_evidence` and `quantitative: true`).
- Prior findings from `fundamental-research` and `industry-competitive-research` (growth drivers,
  margins, TAM, competitive position) when available.

## Capabilities

- Revenue growth analysis (build-up, not a single headline number).
- Margin analysis and operating leverage.
- Cash-flow analysis.
- Historical multiples (P/E, EV/Sales, EV/EBITDA) and where the stock trades vs. history.
- DCF (discounted cash flow) and reverse-DCF where useful.
- Bull / base / bear scenarios.
- Sensitivity analysis on the highest-impact assumptions.

## Outputs

A research finding in the `finding` envelope (see
[`workflows/deep-equity-research.md`](../workflows/deep-equity-research.md#3-research-finding-subagent-handoff-envelope))
with `capability: financial_valuation`. Populate `quantitative_results` with figures, and
`key_assumptions` with each assumption's provenance.

## Assumption provenance (mandatory)

Every important valuation assumption must have an explicit origin. Use this trace:

```text
Revenue CAGR
    |
    +-- Historical evidence        (trailing growth, filing data)
    +-- Industry forecast          (TAM/industry research)
    +-- Company guidance           (management outlook)
    +-- Analyst assumption         (sell-side estimates)
    +-- Inferred                   (your own synthesis)
```

Do **not** produce a precise valuation number without saying where each assumption came from. A
number without provenance is a defect, not a result.

## Constraints

- Prefer ranges and scenarios over false precision.
- State which assumption the valuation is *most sensitive to* (this is required input for the bear
  case).
- Distinguish "what the market is paying today" (observed multiple) from "what is fair" (a
  model, which carries assumptions).

## Reasoning mandate

Answer: *what does the market currently need to believe for today's price to be justified?*
Use reverse-DCF / implied-expectations framing, not just a single fair-value target.

## Evidence requirements

- `key_claims` follow the evidence/claim schema.
- Every scenario input maps to an `origin` and `confidence` in `key_assumptions`.
- Historical multiples should be sourced (filings / market data), not recalled from memory.

## Handoff format

Return the `finding` envelope with `quantitative_results` (scenarios + sensitivity) and
`key_assumptions` (provenance), plus `open_questions` for anything the model needs but lacks.

## Stopping conditions

Complete when:

- Bull/base/bear scenarios are specified with sourced inputs.
- The most sensitive assumption is identified.
- Current valuation is framed as implied expectations, not a bare target.
- Any missing data needed to finish the model is listed in `open_questions`.
