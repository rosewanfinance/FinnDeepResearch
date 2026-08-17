# Skill: Fundamental Research

## Purpose

Analyze the company's business model and fundamental drivers: how it makes money, how fast it is
growing, and what is sustainable about that growth.

## Inputs

- A `sub_question` from the research plan (with its `required_evidence`).
- The company/ticker under analysis.

## Focus areas

- Revenue segmentation (by product / geography / customer type).
- Volume / price / mix dynamics.
- Gross, operating, and net margins; operating leverage.
- Cash flow and capital expenditure.
- Business segments and their relative contribution.
- Customer concentration.
- Fundamental growth drivers (new products, pricing power, capacity, attach rates).

## Outputs

A research finding in the `finding` envelope defined in
[`workflows/deep-equity-research.md`](../workflows/deep-equity-research.md#3-research-finding-subagent-handoff-envelope),
with `capability: fundamentals`. `key_claims` uses the evidence/claim schema.

## Distinguishing statement types (mandatory)

Every assertion must be tagged as exactly one of:

| Tag | Meaning |
|---|---|
| `observed_fact` | Verifiable from primary data (filings, reported figures). |
| `management_claim` | Stated by company management, not independently verified. |
| `analyst_assumption` | A sell-side/buy-side estimate or projection. |
| `inferred_conclusion` | Your own synthesis from the above — clearly labeled as inference. |

A finding that leans heavily on `management_claim` or `inferred_conclusion` without `observed_fact`
support must be flagged accordingly (this is what the evidence-analysis skill will attack).

## Constraints

- Do not build a valuation here; leave price/multiple work to `financial-valuation`.
- Do not speculate beyond the data; mark uncertainty explicitly.
- Report both what is known and what is *not* known (data gaps).

## Reasoning mandate

Explain *why* the business grows or does not grow — identify the driver and whether it is durable.
Prefer primary sources (10-K/10-Q, earnings transcripts, investor materials) over secondary
summaries.

## Evidence requirements

- Each `key_claim` must carry a source, source type, publication date, and confidence (see the
  evidence/claim schema).
- Figures should be tied to a specific filing or transcript, not a vague "recent quarter".

## Handoff format

Return the `finding` envelope as structured markdown/YAML. Put `open_questions` explicitly so the
Director knows what remains to resolve.

## Stopping conditions

This skill's work is complete when:

- Revenue segmentation and the growth driver are quantified with sources.
- Margins / cash flow / capex are covered at the level the sub-question requires.
- Statement-type tags are applied to all key claims.
- `open_questions` lists anything important that could not be answered from available sources.
