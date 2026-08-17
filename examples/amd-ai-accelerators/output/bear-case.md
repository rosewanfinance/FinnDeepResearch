# Bear Case — AMD / AI Accelerator Market

```yaml
bear_case:
  thesis: >
    AMD's ~$838B market cap (~97x forward earnings) is justified because AMD will roughly triple
    AI-accelerator share from ~5% today to ~15-17% by 2029, driving Data Center revenue from ~$29B
    (FY2026E) to ~$86-101B (FY2029) at NVIDIA-like margins.

  priced_in: >
    The reverse-DCF shows the current price ALREADY embeds ~15-17% share by 2029 and a ~30x exit
    multiple. "AMD wins share" is consensus, not a differentiated view — the stock only works if AMD
    hits the share target AND does so at NVIDIA-like margin AND the TAM reaches $286-446B AND the
    multiple holds. PRICED: the AI-capex-cycle risk and the headline share win (the 9% post-earnings
    drop shows the market is already skittish on margin). UNDERAPPRECIATED: (1) the equity-dilutive
    warrant structure means won share leaks economics to buyers; (2) AMD's anchor customers are
    simultaneously building their own ASICs; (3) AMD DC operating income FELL YoY in 2025 while
    revenue rose — margin was already sacrificed to win share.

  challenges:
    - critical_assumption: "AI-accelerator share triples ~5% → ~15-17% by 2029."
      counter_evidence: "Share flat ~4-6% through 2025 (IDC: NVIDIA ~72%, AMD ~5.8%); Meta/OpenAI/Microsoft/Anthropic deals are forward commitments, not revenue; JPMorgan forecasts ASIC shipments overtake GPUs by 2027."
      failure_scenario: "Anchor commitments convert below guided levels as buyers use AMD as price leverage while ramping internal ASICs; share stuck at 6-8%."
      potential_impact: "High — the 15-17% share is the base case in the price; missing it de-rates the ~$838B / 97x valuation."
      monitor: "Quarterly IDC/Omdia share; conversion of commitments to PO revenue; FY2027 DC guidance; hyperscaler reallocation to internal silicon."
      likelihood: high
      severity: high
    - critical_assumption: "The won share carries NVIDIA-like margin."
      counter_evidence: "9M-2025 DC op income FELL YoY while revenue rose; Q2 2026 margin guide disappointed (stock -9%); SemiAnalysis: Meta/OpenAI warrants up to 160M shares could render GPUs near-zero-cost to buyers; $4.75B debt raise adds fixed-cost leverage."
      failure_scenario: "Warrants vest and dilute; MI450/MI500 margin stays well below NVIDIA; DC revenue grows but DC op income does not (2025 pattern recurs)."
      potential_impact: "High — highest sensitivity; if the margin leg is half of assumed, EPS is a fraction of consensus even on the bull revenue path."
      monitor: "DC segment op margin quarterly; share-count creep; MI450/MI500 GM commentary; whether DC op income re-accelerates."
      likelihood: high
      severity: high
    - critical_assumption: "AI accelerator TAM grows durably to $286-446B by 2029."
      counter_evidence: "Omdia's Aug 2024 forecast was only $151B and warned growth 'slows sharply beyond 2026'; JPMorgan flags power + ROI as binding constraints; training capex is debt-financed."
      failure_scenario: "TAM lands near $151B as training capex peaks and power/ROI bind; simultaneous 6GW commitments can't all be powered/monetized."
      potential_impact: "High — at $151B TAM, even 15% share is ~$23B, under a third of the $86-101B target."
      monitor: "Hyperscaler capex guidance; Omdia/Gartner TAM revisions; PPA/grid announcements; capex-digestion commentary."
      likelihood: high
      severity: high
    - critical_assumption: "Custom silicon does not cap AMD's merchant share."
      counter_evidence: "Google TPU, AWS Trainium, Microsoft Maia, Meta MTIA/Iris, OpenAI XPU all ramp in parallel; every AMD anchor buyer builds its own ASIC; JPMorgan ASIC>GPU 2027 hits AMD (the marginal merchant) hardest."
      failure_scenario: "Deals prove to be hedging/price-leverage; committed AMD volume reprioritized as internal silicon reaches production."
      potential_impact: "Medium-high — 15-17% of a shrinking merchant pie is far smaller than assumed."
      monitor: "Broadcom/Marvell ASIC backlog; Meta/OpenAI/Microsoft/Anthropic silicon deployment; % DC revenue from top buyers."
      likelihood: high
      severity: medium
    - critical_assumption: "CUDA/ROCm software gap does not cap enterprise share."
      counter_evidence: "SemiAnalysis: NVIDIA inference software lead WIDENING (vLLM >12k tok/s); ~6M CUDA developers; ROCm still has correctness/perf gaps."
      failure_scenario: "Enterprise/second-tier buyers keep buying NVIDIA; AMD share stays concentrated in price-sensitive hyperscalers who are building ASICs."
      potential_impact: "Medium — structurally links share win and margin win; caps total addressable share."
      monitor: "ROCm adoption metrics; SemiAnalysis benchmark reports; AMD enterprise DC mix."
      likelihood: medium
      severity: medium
    - critical_assumption: "The ~30x exit multiple holds."
      counter_evidence: "~97x forward earnings is ~2x AMD's own prior peak; stock already dropped 9% on a margin guide; exit multiple assumes AI doesn't mature into a cyclical hardware regime."
      failure_scenario: "As AI capex matures post-2027, AI hardware re-rates from growth to cyclical multiples; AMD compresses from ~30x toward 18-20x."
      potential_impact: "High — ~30x → ~18-20x halves the target with no revenue miss required."
      monitor: "AMD forward P/E vs 5-yr avg; sell-side dispersion on AI capex sustainability; stock reaction to next margin guide."
      likelihood: high
      severity: high

  most_important_risk: >
    The share win is already priced in at NVIDIA-like economics, but AMD is winning that share through
    equity-dilutive warrant structures granted to customers who are simultaneously building their own
    ASICs — so even hitting the ~15-17% share and ~$86-101B revenue target produces far less per-share
    earnings than the ~97x multiple implies. The evidence that DC operating income FELL YoY in 2025
    while revenue rose, plus the warrant dilution, means the margin leg of the thesis is already
    falsifying before the tripling has occurred.

  invalidation_condition: >
    AMD reports a quarter in which Data Center segment operating margin again fails to inflect toward
    NVIDIA-like levels — DC operating income declining YoY on rising revenue (a repeat of the 2025
    pattern at scale) or DC operating margin remaining below ~25-30% vs NVIDIA's ~65-70% in
    FY2026/FY2027 — OR any anchor customer (Meta, OpenAI, Microsoft, Anthropic) publicly reallocating a
    material tranche of its committed AMD GPU capacity to internal ASICs.
```

## Verification note

The warrant structure (up to 160M shares, dilutive direction) is corroborated by multiple
SemiAnalysis-derived outlets (high confidence on existence, medium on exact strike/vesting). The precise
"9M-2025 DC op income fell YoY" figure is from the Q3 2025 10-Q snippet (`$1.9B` 9M-2025 vs `$2.3B`
9M-2024). The "160M / $600-700" terms are second-hand — treat the exact numbers as medium confidence.
