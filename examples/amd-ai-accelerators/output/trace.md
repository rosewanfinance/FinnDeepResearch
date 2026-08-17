# Execution Trace — AMD / AI Accelerator Market

Research question:
> Is AMD's current valuation justified by its expected share gains in the AI accelerator market over the next three years?

Round budget (stated up front): ≤ 2 parallel research waves, ≤ 2 recursive deep-dives, 1 evidence audit, 1 bear case. Stop a branch when importance is low **and** confidence is high, or when further research would not change the thesis.

## Decisions

### T0 — Understand & plan
- Read `orchestration/director.md`, `workflows/deep-equity-research.md`, all 5 skills, all 5 agents, and the example templates.
- Question is a **share-gain** story (center of gravity = competitive capture vs. NVIDIA's CUDA moat + custom silicon), not a pure TAM-growth story. This dictates the plan's emphasis.
- Named the falsifiable thesis hypothesis:
  > AMD's premium forward multiple is justified only if Instinct/Data Center revenue can grow via sustained accelerator share gains against CUDA lock-in and hyperscaler custom silicon over 2026–2029.
- Wrote `plan.md` with 7 sub-questions, capabilities, dependencies, required evidence, and controversial assumptions. Planned evidence:
  - `plan.md` (this trace's plan counterpart).

### T1 — Wave 1 spawn (parallel, 6 agents)
Spawned in parallel, one sub-question each:

| question_id | capability | rationale |
|---|---|---|
| `dc-segment-fundamentals` | fundamentals | Establish Data Center size/margin/cash-flow/customer concentration baseline |
| `instinct-ramp-design-wins` | fundamentals | The core of the share-gain thesis: is announced wins → realized revenue real? |
| `accelerator-tam` | industry_competitive | Market backdrop and 3-yr growth, training vs inference |
| `accelerator-market-share` | industry_competitive | Explicit market-growth vs share-gain attribution |
| `cuda-moat-rocm` | industry_competitive | Highest-importance/lowest-confidence candidate: software as binding constraint |
| `hyperscaler-custom-silicon` | industry_competitive | Custom-silicon squeeze on AMD's addressable opportunity |

Dependency handling: `valuation-implied-expectations` is held for Wave 2 (needs fundamentals + share + TAM inputs). All Wave-1 agents are independent and run concurrently.

### T2 — Wave 1 results received (all 6)
| question_id | capability | confidence | headline |
|---|---|---|---|
| `dc-segment-fundamentals` | fundamentals | medium | DC $6.7B Q2'26 (~58% of rev); op margin ~30% through 2025 compressing in 2026 on Helios ramp; one customer ~24% FY24; hyperscalers + OpenAI dominant |
| `instinct-ramp-design-wins` | fundamentals | **low** | Instinct ~$0→>$5B(2024)→~$10B(2025); 2023–24 wins converted, 2025–26 mega-deals (OpenAI/Anthropic) NOT yet realized; possible 2026 re-segmentation |
| `accelerator-tam` | industry_competitive | medium | TAM ~$150–200B(2025)→$286–446B(2029); durable inference base + cyclical training |
| `accelerator-market-share` | industry_competitive | medium | AMD share ~4–6%, flat since 2024 step-up; growth = MARKET GROWTH, not share gain; double-digit share is `management_only` |
| `cuda-moat-rocm` | industry_competitive | medium | CUDA moat deep; software NOT binding on top-tier wins but binding on broad share; NVIDIA inference lead widening; Meta warrant (8-K) confirmed |
| `hyperscaler-custom-silicon` | industry_competitive | medium | NVIDIA ~80%, custom ASIC fastest (ASIC>GPU units by 2027), AMD = merchant second source (Meta/OpenAI/Microsoft); warrant economics + 9% post-earnings selloff surfaced |

Method caveat (all agents): WebFetch blocked network-wide; figures from WebSearch snippets + multi-outlet corroboration. Carried into audit.

### T3 — Evaluation of intermediate results

**Contradiction detected (high importance, low confidence).** The two fundamentals findings are
internally inconsistent about AMD's Data Center revenue base:
- `dc-segment-fundamentals`: Q2 2025 DC = **$4,344M** → Q2 2026 $6.7B = **+54% YoY**; Q1 2025 = $4,123M → Q1 2026 ~$6.5B = +57%. Implies FY2025 DC ≈ $20B.
- `instinct-ramp-design-wins`: 2025 DC quarterly = Q1 $4.15B / Q2 **$6.09B** / Q3 $7.4B / Q4 $8.4B (FY2025 ≈ $26B); then Q1'26 "Data Center $5,380M" + Q2'26 "$6.7B" with "doubled" headlines — irreconcilable unless AMD re-segmented.

The two agents also disagree on the *nature* of any 2026 re-segmentation (merge Gaming→"Client and
Gaming" vs. split Instinct out of Data Center). This determines whether the 2026 ramp is **decelerating
(+54%)** or **accelerating (doubling)** — load-bearing for the valuation. Per the manual, investigate
the conflict rather than averaging.

Also noted: a 2025→2026 timing tension between `accelerator-market-share` (share flat through 2025) and
`hyperscaler-custom-silicon` (share gains on new 2026 Meta/OpenAI/Microsoft deals) — reconcilable as a
timing inflection, but flagged for the audit.

### T4 — Deep-dive decision

**Spawned 1 recursive deep-dive** (`amd-dc-revenue-reconciliation`, fundamentals) to settle the DC
revenue base / re-segmentation / Instinct trajectory contradiction — the single highest-value open
question for the valuation.

**Spawned evidence-analysis** in parallel, pointed at `output/findings/*.md`, to audit claim quality,
flag weak/management-only claims, and enumerate contradictions.

Round budget: 1 of ≤2 deep-dives used.

### T5 — Wave 2: valuation
**Deep-dive resolved the contradiction (high confidence, primary 10-K/10-Q citations):**
- FY2025 Data Center = **$16.6B** (+32%), NOT ~$26B.
- Q2 2025 DC = **$3.2B** (+14%, depressed by China "chips curb"); Q2 2026 DC = **$6.7B** (+107%, "doubling" partly a weak-base effect).
- Re-segmentation = Client+Gaming merged **effective Q1 2025**; no Instinct split. DC definition unchanged.
- Margin compression began **in 2025** (9M25 DC op income fell YoY while revenue rose), not 2026.
- Instinct re-accelerating (+22%→+29%→+32%→+107%), but flattered by the weak Q2 2025 base.

Spawned `valuation-implied-expectations` (financial_valuation) with these reconciled inputs + the share,
warrant, TAM, and custom-silicon findings. It must frame today's price as implied expectations and name
the single most sensitive assumption.

### T6 — Bear case
**Valuation verdict:** ~97x forward P/E / ~$838B market cap. Reverse-DCF implies AMD must roughly triple
accelerator share (~5% → ~15-17% by 2029) at ~35% net margin; the flat-share scenario is worth ~$400B
(~half the price). Most sensitive assumption = 2029 share; second-order = margin. This is a
"fully-priced share-gain" situation, not a market-growth discount.

Spawning `bear-case` on the refined thesis (share triples to ~15-17% at NVIDIA-like margins) to
challenge each critical assumption and define `most_important_risk` + `invalidation_condition`.

### T7 — Final synthesis → memo.md

**Bear case returned.** `most_important_risk`: the share win is priced in at NVIDIA-like economics, but
AMD is winning it through equity-dilutive warrants granted to customers who are simultaneously building
their own ASICs — so even hitting ~15-17% share produces far less per-share earnings than the ~97x
multiple implies; the margin leg is already falsifying (2025 DC op income fell YoY). `invalidation_condition`:
a quarter where DC operating margin fails to inflect (DC op income down YoY on rising revenue, or margin
<25-30% vs NVIDIA ~65-70%) OR an anchor customer reallocating a material tranche of AMD GPU capacity to
internal ASICs.

**Verdict (synthesized):** **Not justified on current evidence.** The ~97x forward P/E / ~$838B cap is a
fully-priced share-gain bet, not a market-growth discount. Reverse-DCF shows the price embeds a ~15-17%
share (a tripling from the flat ~5% AMD actually holds), at NVIDIA-like margins, under a $286-446B TAM,
at a ~30x exit multiple — four simultaneous legs with no margin of safety. Flat-share scenario ≈ $400B
(~−50%). Downside risk is asymmetric.

**All 12-section artifacts written:** `plan.md`, `trace.md`, `findings/` (7 files incl. the deep-dive),
`evidence-audit.md`, `bear-case.md`, `memo.md`.

### Final trace summary

```text
Research Director
  ↓
Created 7 sub-questions (plan.md) — thesis framed as falsifiable hypothesis
  ↓
Wave 1: 6 parallel agents (fundamentals ×2, industry/competitive ×4)
  ↓
Evaluation → 4 contradictions detected, esp. Data Center revenue base (high importance, low confidence)
  ↓
Deep-dive (fundamental-research) resolved the revenue base from primary 10-K/10-Q:
    FY2025 DC = $16.6B (not ~$26B); Q2'25 = $3.2B (China "chips curb"); margin compressed in 2025
  + evidence-analysis audit (13 flagged claims, 4 contradictions, confidence low) run in parallel
  ↓
Wave 2: valuation (reverse-DCF) — price embeds ~15-17% share, ~$400B flat-share counterfactual
  ↓
Bear case — margin dilution + warrant economics + customer-ASIC internalization + multiple de-rating
  ↓
Final synthesis → memo (12 sections) + bull/base/bear + monitoring indicators + invalidation condition
```

Budget consumed: 2 research waves, 1 recursive deep-dive (of ≤2 allowed), 1 evidence audit, 1 bear case.

