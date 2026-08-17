# Skill: Industry & Competitive Research

## Purpose

Understand the external environment surrounding the company — the market, the ecosystem, and the
competitive dynamics — rather than just the company itself.

## Inputs

- A `sub_question` from the research plan (with its `required_evidence`).
- The company/ticker and its relevant industry/ecosystem.

## Focus areas

- Total addressable market (TAM) and its growth rate.
- Industry growth vs. company growth (market growth vs. share gain).
- Supply / demand balance.
- Market share and its trajectory.
- Competitors and their positioning.
- Substitutes and technology transitions.
- Pricing dynamics.
- Customer behavior and ecosystem / network effects.

## Outputs

A research finding in the `finding` envelope (see
[`workflows/deep-equity-research.md`](../workflows/deep-equity-research.md#3-research-finding-subagent-handoff-envelope))
with `capability: industry_competitive`. It **must** populate:

- `growth_attribution` — a direct answer to:

> Is the company's growth primarily driven by **market growth**, **market-share gain**, or **both**?

For NVIDIA-style questions, investigate the broader AI infrastructure ecosystem (hyperscaler capex,
chip demand, foundry/co-packaging constraints, competitive entrants), not just NVIDIA headlines.

## Constraints

- Keep the company in context, but the unit of analysis is the *industry/ecosystem*.
- Distinguish structural demand (durable) from cyclical/one-off demand (transient).
- Do not produce a valuation or a company DCF.

## Reasoning mandate

Identify the forces that determine how large and how durable the opportunity is, and where the
company sits within that opportunity. Look for the constraint that caps growth (supply, demand,
capital, technology).

## Evidence requirements

- `key_claims` follow the evidence/claim schema (source, source type, date, confidence).
- Market-share or TAM figures must cite a concrete source or methodology, not an unqualified number.
- Note where industry forecasts disagree (this feeds the evidence/contradiction analysis).

## Handoff format

Return the `finding` envelope with `growth_attribution` filled in and `open_questions` explicit.

## Stopping conditions

Complete when:

- `growth_attribution` is answered with evidence.
- TAM / industry growth / competitive position are covered at the required depth.
- Key competitors/substitutes and the binding constraint on growth are identified.
- Unresolved competitive uncertainties are listed in `open_questions`.
