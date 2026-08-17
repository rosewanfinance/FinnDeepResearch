# Benchmark Question

> **Is NVIDIA's current valuation justified by the expected growth of AI infrastructure spending
> over the next three years?**

## Why this question

This is the primary demonstration because it cannot be answered well by a single-pass LLM. It
requires, at minimum:

- **Company research** — NVIDIA's data-center revenue, margins, and growth drivers.
- **Industry research** — the AI infrastructure / accelerated-computing TAM and growth rate.
- **Hyperscaler spending analysis** — the CapEx cycle of the largest buyers and its sustainability.
- **Competitive analysis** — AMD, custom silicon (TPUs/ASICs), and potential entrants.
- **Financial analysis** — margin structure, cash flow, and operating leverage.
- **Valuation** — whether the current multiple implies growth the market must still believe.
- **Scenario analysis** — bull/base/bear paths for AI CapEx over three years.
- **Evidence validation** — separating observed data from management and analyst claims.
- **Bear-case analysis** — what would overturn the growth thesis.

It therefore exercises every Skill in the prototype, which is the point: it demonstrates *why*
multi-agent, adaptive research is useful.

## Expected run

To run this example, start a Claude Code session and tell it to act as the Research Director
following [`orchestration/director.md`](../../orchestration/director.md). See
[`README.md`](README.md) for the artifacts a complete run should produce.
