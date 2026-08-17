# Finding — valuation-implied-expectations (financial_valuation)

```yaml
finding:
  question_id: valuation-implied-expectations
  question: "What share-gain and growth trajectory does AMD's current valuation already imply, and is that justified under bull/base/bear scenarios?"
  capability: financial_valuation

  answer: >
    AMD trades at a record ~97x forward P/E and ~21x trailing EV/Sales — roughly double its prior
    5-year peak multiple — and the reverse-DCF shows today's ~$838B market cap already prices in AMD
    roughly tripling AI-accelerator market share from ~5% today to ~15-17% by 2029 (Data Center revenue
    compounding ~44-51% from ~$29B in FY2026 to ~$86-101B). The valuation does NOT merely price "ride
    the TAM at ~5% share": that scenario is worth only ~$400B, i.e. ~half the current price. Share gain
    is not just the thesis — it is already fully priced in, and the bear case is that the share being won
    is margin-dilutive (2025 DC margin compression, disappointing 2026 margin guide), which would force
    the revenue bar even higher than the model assumes.

  key_claims:
    - claim: "AMD trades at ~97x forward earnings, versus ~21x for NVIDIA."
      source: "Motley Fool / Nasdaq"
      source_type: sell_side
      publication_date: "2026-06-25"
      supporting_evidence: "Headline; live forward multiple ~95-100x."
      confidence: medium
    - claim: "AMD market cap ~$831-840B on ~1.63B basic shares (~$514/share); diluted ~1.79B incl. up to 160M Meta warrants → ~$920B fully-diluted."
      source: "financecharts.com; AMD 8-K"
      source_type: third_party
      publication_date: "2026-08"
      supporting_evidence: "$514 × 1.63B = $838B."
      confidence: medium
      flags: [weak_source]
    - claim: "Q2 2026: record $11.5B (+50%), DC $6.7B (+107% vs depressed Q2'25 base); stock fell ~9-10% on margin guide, recovered on $4.75B bond sale."
      source: "mitrade / Yahoo / Nasdaq"
      source_type: news
      publication_date: "2026-08-05 to 2026-08-15"
      supporting_evidence: "Consistent news reports."
      confidence: high
    - claim: "AMD 2025 Instinct revenue ~$8B (JPMorgan); HSBC 2026 AI-GPU ~$19.8B (~1/10th NVIDIA's ~$185-190B DC)."
      source: "JPMorgan; HSBC"
      source_type: sell_side
      publication_date: "2026"
      supporting_evidence: "Reconciled inputs."
      confidence: medium
    - claim: "AI accelerator TAM ~$150-200B (2025) → $286B (Omdia) / $446B (Dell'Oro) by 2029."
      source: "Omdia; Dell'Oro"
      source_type: third_party
      publication_date: "2026"
      supporting_evidence: "Reconciled inputs."
      confidence: medium
    - claim: "AMD AI-accelerator share ~4-6%, roughly FLAT through 2025."
      source: "Reconciled prior findings"
      source_type: third_party
      publication_date: "2026"
      supporting_evidence: "Consistent with ~$8B Instinct / ~$150-200B TAM."
      confidence: medium

  key_assumptions:
    - { assumption: "Share price ~$514.", origin: news_snippet, confidence: medium }
    - { assumption: "Basic shares ~1.63B; diluted ~1.79B.", origin: filing, confidence: medium }
    - { assumption: "Net debt ~$0.5B; EV ~$840B.", origin: inferred, confidence: low }
    - { assumption: "FY2026 revenue ~$47B (+~35%).", origin: company_guidance, confidence: medium }
    - { assumption: "FY2026 non-GAAP EPS ~$5.0-5.5 (95-100x forward).", origin: analyst, confidence: low }
    - { assumption: "FY2026 Data Center ~$29B.", origin: inferred, confidence: medium }
    - { assumption: "Reverse-DCF: 10% cost of equity, 3.4y to FY2029, 30x exit P/E, 35% net margin.", origin: inferred, confidence: medium }
    - { assumption: "FY2029 net margin 30-40%.", origin: inferred, confidence: low }
    - { assumption: "DC = 78% of FY2029 revenue; accelerator = 60% of DC.", origin: inferred, confidence: low }

  quantitative_results:
    - metric: "Valuation snapshot (2026-08-17)"
      figures:
        - { item: "Market cap", value: "~$838B basic / ~$920B diluted", confidence: medium }
        - { item: "Forward P/E (FY26E)", value: "~95-100x", confidence: low }
        - { item: "EV/TTM sales", value: "~21x", confidence: low }
        - { item: "EV/FY2026E sales", value: "~18x", confidence: low }
    - metric: "Reverse-DCF (10% DR, 30x exit, 35% margin)"
      figures:
        - { item: "Required FY2029 market cap", value: "$1,158B" }
        - { item: "Implied FY2029 net income", value: "$39B" }
        - { item: "Implied FY2029 revenue", value: "$95-132B (27-40% CAGR)" }
        - { item: "Implied FY2029 Data Center", value: "$86-103B (44-51% CAGR)" }
        - { item: "Implied FY2029 accelerator share", value: "15-22% of Omdia $286B; midpoint ~17%" }
    - metric: "Scenarios (FY2029)"
      figures:
        - { item: "BEAR (no share gain)", value: "share ~7% → $20B accel; DC ~$40-44B; fair value ~$400B (~half of actual)" }
        - { item: "BASE (modest gain)", value: "share ~11% → $31.5B; DC ~$55B (24% CAGR)" }
        - { item: "BULL (priced-in)", value: "share ~16% → $46B; DC ~$74B (37% CAGR)" }
    - metric: "Flat-share counterfactual"
      figures:
        - { item: "Value at ~7% share", value: "FY2029 rev ~$59B, NI ~$20B, PV ~$398B vs $838B actual → stock ~110% above no-share-gain value" }

  most_sensitive_assumption: >
    2029 AI-accelerator market share (~15-17% embedded vs ~5% today); second-order: the operating
    margin earned on that share (2025 DC op income FELL while revenue rose; Q2'26 margin guide disappointed).

  verdict: >
    The valuation prices in SHARE GAIN as its center of gravity, not "market growth at ~5% share." The
    reverse-DCF shows the market must believe AMD's accelerator share roughly triples to ~15-17% by 2029
    (DC compounding ~44-51%), materially above the flat ~4-6% share held through 2025 and not yet backed
    by realized revenue. If share-gain stalls → de-rates toward ~$400B (~half). If AMD delivers ~16%
    share, today's price merely delivers ~10% annual return with little margin of safety.

  open_questions:
    - "Exact FY2026/FY2027 consensus EPS/revenue (WebFetch blocked)."
    - "Exact cash/debt as of Q2 2026 for precise EV."
    - "Precise 5-year forward P/E and EV/Sales high/low from a paid source."
    - "AMD Q3/Q4 2026 Data Center guidance."
    - "DC operating-margin trajectory (key bear input)."
    - "Meta warrant timing/dilution."

  confidence: medium
```

## Director note

The reverse-DCF is the crux of the answer: at ~97x forward earnings, the price **already assumes** the
share-gain thesis succeeds (~15-17% share, ~3x today). The flat-share scenario is worth ~$400B, half the
actual $838B. So the question is not "is the share-gain story real?" but "is the story *better than the
market already prices*, and can it be won at acceptable margins?" — the two things the bear case must now
test.
