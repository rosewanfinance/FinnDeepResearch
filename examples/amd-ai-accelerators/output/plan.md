# Research Plan — AMD / AI Accelerator Market

```yaml
research_question: "Is AMD's current valuation justified by its expected share gains in the AI accelerator market over the next three years?"
decision_to_support: "Whether AMD's current valuation reflects a defensible AI-accelerator share-gain trajectory (supporting a long/neutral/hold view) or prices in share capture that the evidence does not support."
investment_thesis_hypothesis: "AMD's premium forward multiple is justified only if its Data Center / Instinct revenue can grow via sustained AI-accelerator market-share gains against NVIDIA's CUDA moat and hyperscaler custom silicon over 2026–2029 — a hypothesis to be tested, not assumed."

sub_questions:
  - id: dc-segment-fundamentals
    question: "What is the current size, growth rate, margin structure, and customer concentration of AMD's Data Center segment?"
    required_capabilities: [fundamentals]
    priority: high
    dependencies: []
    required_evidence: "Segment-level revenue (Data Center vs Client vs Gaming vs Embedded) across the last 8 quarters from 10-Q/10-K; segment gross/operating margins; R&D spend; operating cash flow; top-customer concentration."
    quantitative: true
    controversial_assumptions: ["Data Center gross margin can expand toward NVIDIA-like levels", "Data Center growth is durable rather than a one-quarter pull-forward"]

  - id: instinct-ramp-design-wins
    question: "How fast is AMD's Instinct accelerator revenue ramping, and what is the evidence that announced design wins are converting into realized revenue?"
    required_capabilities: [fundamentals]
    priority: high
    dependencies: [dc-segment-fundamentals]
    required_evidence: "Instinct (MI300/MI325/MI350/MI355/MI400) revenue run-rate and quarterly trajectory; management guidance vs. realized revenue; named hyperscaler/enterprise design wins and which have converted to observed revenue."
    quantitative: true
    controversial_assumptions: ["Announced design wins equal realized revenue", "AMD can sustain Instinct unit economics while scaling volume"]

  - id: accelerator-tam
    question: "What is the size and 3-year growth outlook of the AI accelerator market (training + inference), and how much of the demand is durable vs. cyclical?"
    required_capabilities: [industry]
    priority: high
    dependencies: []
    required_evidence: "TAM estimate(s) with named source and methodology; 3-year growth forecasts from at least two independent sources; training-vs-inference demand split; explicit note of where forecasts disagree."
    quantitative: true
    controversial_assumptions: ["AI accelerator TAM keeps growing at current rates through 2029", "Inference demand offsets any training-driven slowdown"]

  - id: accelerator-market-share
    question: "What is AMD's current AI accelerator market share and its trajectory, and is AMD's growth primarily market growth or share gain?"
    required_capabilities: [industry]
    priority: high
    dependencies: [accelerator-tam]
    required_evidence: "Market-share estimates (NVIDIA vs AMD vs custom silicon) with source and methodology; share trajectory over recent quarters; explicit growth-attribution answer (market growth vs share gain vs both)."
    quantitative: true
    controversial_assumptions: ["AMD is actually gaining accelerator share vs. merely growing with the market", "Third-party share estimates are accurate enough to support the thesis"]

  - id: cuda-moat-rocm
    question: "How strong is NVIDIA's CUDA software moat, how mature is AMD's ROCm ecosystem, and does software remain the binding constraint on AMD's share capture?"
    required_capabilities: [industry]
    priority: high
    dependencies: []
    required_evidence: "Evidence on CUDA lock-in economics (developer base, library depth); ROCm adoption, gaps, and roadmap; enterprise/inference vs. training software readiness; signs of or barriers to software-driven switching."
    quantitative: false
    controversial_assumptions: ["ROCm reaches 'good enough' parity to break CUDA lock-in", "Inference workloads are less software-locked than training"]

  - id: hyperscaler-custom-silicon
    question: "How are hyperscalers allocating AI accelerator capex across NVIDIA, AMD, and in-house custom silicon (TPU/Trainium/Maia), and is custom silicon a growing threat to AMD's addressable opportunity?"
    required_capabilities: [industry]
    priority: high
    dependencies: []
    required_evidence: "Hyperscaler capex allocation evidence across NVIDIA/AMD/custom silicon; custom-silicon roadmap and expected volume; AMD's customer base and concentration among the largest buyers."
    quantitative: true
    controversial_assumptions: ["Merchant silicon (AMD/NVIDIA) retains share vs. in-house ASICs", "AMD's hyperscaler relationships are durable and expanding"]

  - id: valuation-implied-expectations
    question: "What share-gain and growth trajectory does AMD's current valuation already imply, and is that justified under bull/base/bear scenarios?"
    required_capabilities: [financial_valuation]
    priority: high
    dependencies: [dc-segment-fundamentals, accelerator-market-share, accelerator-tam]
    required_evidence: "Current forward P/E and EV/Sales vs. 5-year history (sourced); reverse-DCF/implied-expectations framing of today's price; bull/base/bear scenarios with every input carrying an origin; identification of the single most sensitive assumption."
    quantitative: true
    controversial_assumptions: ["AMD sustains a growth-adjusted premium multiple", "Data Center revenue sustains 30%+ CAGR through 2029"]
```

## Execution notes

- **Wave 1 (parallel):** `dc-segment-fundamentals`, `instinct-ramp-design-wins`,
  `accelerator-tam`, `accelerator-market-share`, `cuda-moat-rocm`, `hyperscaler-custom-silicon`.
- **Wave 2:** `valuation-implied-expectations`, fed with synthesized inputs from Wave 1.
- **Wave 3:** evidence audit on assembled claims; recursive deep-dive on any
  high-importance / low-confidence branch (candidate: design-win → revenue conversion,
  and CUDA-moat / ROCm maturity).
- **Wave 4:** bear-case challenge, then final 12-section memo + trace.

**Round budget (stated explicitly):** ≤ 2 parallel research waves, ≤ 2 recursive deep-dives,
1 evidence audit, 1 bear case. A branch stops when importance is low and confidence is high,
or when further research would not change the thesis.
