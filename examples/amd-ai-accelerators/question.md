# Benchmark Question

> **Is AMD's current valuation justified by its expected share of the AI accelerator market over
> the next three years?**

## Why this question

A strong second demonstration because its center of gravity is *competitive share capture*, which
complements the NVIDIA example's focus on *TAM growth and CapEx sustainability*. It requires, at
minimum:

- **Company research** — AMD's Data Center segment (Instinct MI300/MI350, EPYC), revenue mix, and
  margin trajectory.
- **Industry research** — the AI accelerator TAM and its growth rate, split by training vs.
  inference demand.
- **Hyperscaler spending** — how cloud capex is allocated across NVIDIA, AMD, and in-house custom
  silicon (TPU / Trainium / Maia).
- **Competitive analysis** — NVIDIA's CUDA moat and roadmap, AMD's software ecosystem (ROCm),
  custom-silicon threats, and Intel.
- **Financial analysis** — AMD's structural gross-margin gap vs. NVIDIA, R&D intensity, cash flow,
  and operating leverage.
- **Valuation** — whether AMD's high forward multiple is justified by share capture rather than
  market growth alone.
- **Scenario analysis** — bull/base/bear paths for accelerator market share and pricing.
- **Evidence validation** — separating AMD's stated win-rate / pipeline claims from *observed*
  revenue and design-win conversion.
- **Bear-case analysis** — CUDA lock-in, roadmap-execution risk, custom-silicon squeeze, margin
  compression, and multiple contraction.

The competitive dimension is the hard part: AMD's investment case is a share-gain story against an
entrenched incumbent with a software moat, which is exactly the kind of question a single-pass LLM
tends to answer with vibes rather than evidence.

## Expected run

To run this example, start a Claude Code session and tell it to act as the Research Director
following [`orchestration/director.md`](../../orchestration/director.md). See
[`README.md`](README.md) for the artifacts a complete run should produce.
