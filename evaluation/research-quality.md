# Evaluation: Research Quality

How to judge whether the multi-agent workflow actually improves research quality over a
single-pass LLM. The goal is not to "prove multi-agent is always better" — it is to show that for
complex financial questions, specialization + adaptive orchestration yields a more structured,
defensible process.

## Comparison

| | Baseline | Proposed system |
|---|---|---|
| Shape | Question → LLM → Report | Question → Director → Skills → Evidence analysis → Recursive research → Bear case → Synthesis |
| Evidence | Implicit / unverifiable | Explicit, sourced, confidence-tagged |
| Depth | Fixed, single pass | Adaptive (deepens where uncertain) |
| Validation | None | Adversarial (bear case) |

## Dimensions

Score each 1–5 against the rubric below, for both baseline and proposed system on the same
question (the NVIDIA benchmark).

1. **Research breadth** — number of independent dimensions covered.
2. **Evidence coverage** — share of important claims with explicit support.
3. **Source quality** — proportion of primary/high-reliability sources.
4. **Factual consistency** — absence of internal contradictions.
5. **Numerical accuracy** — figures are correct and traceable to a source.
6. **Citation quality** — sources are specific, dated, and verifiable.
7. **Contradictory evidence discovered** — whether counter-evidence is surfaced, not buried.
8. **Depth of investigation** — whether important uncertainties were pursued recursively.
9. **Thesis robustness** — whether the conclusion survives the bear case.

## Scoring checklist

For each dimension, ask:

- **Breadth** — Does it cover company, industry, competition, financials, valuation, and risks?
- **Evidence coverage** — For each major claim: is there a source, source type, date, and
  supporting evidence?
- **Source quality** — Filings/transcripts > credible third-party > sell-side > unsourced.
- **Factual consistency** — Are there claims that cannot both be true? Are they flagged?
- **Numerical accuracy** — Can each figure be traced to a filing or report? Are units consistent?
- **Citation quality** — Are sources named and dated, or vague ("analysts say")?
- **Contradictions discovered** — Did it find the strongest counter-evidence, or only confirm the
  thesis?
- **Depth** — Did it recurse into the highest-importance, lowest-confidence uncertainty?
- **Thesis robustness** — Is there an explicit invalidation condition, and does the conclusion
  state what would change it?

## Evidence-quality grading scale

Mirrors [`skills/evidence-analysis.md`](../skills/evidence-analysis.md):

| Confidence | Meaning |
|---|---|
| **High** | Primary source, recent, directly supports the claim. |
| **Medium** | Secondary source or partial support. |
| **Low** | Management-only, outdated, or inferential without support. |

Counts to report: strong claims / weak claims / flagged claims / open contradictions.

## The claim to demonstrate

> For complex financial research questions, specialization and adaptive orchestration can produce
> a more structured and defensible research process than a single-pass LLM response.

The evaluation exists to *support* that claim honestly, not to force it. Where the baseline wins
(e.g. speed, simplicity), say so.
