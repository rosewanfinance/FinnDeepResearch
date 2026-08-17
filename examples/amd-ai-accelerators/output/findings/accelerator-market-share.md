# Finding — accelerator-market-share (industry_competitive)

```yaml
finding:
  question_id: accelerator-market-share
  question: "What is AMD's current AI accelerator market share and its trajectory, and is AMD's growth primarily market growth or share gain?"
  capability: industry_competitive

  answer: >
    AMD's AI accelerator (Instinct data-center GPU) share is low single digits — roughly 4-6% of the
    AI accelerator market by revenue and ~5.8% of deployed cloud AI-accelerator nodes per IDC — versus
    NVIDIA at ~70-90% depending on whether custom ASICs are included, with a fast-growing custom-silicon
    tail (Google TPU/Broadcom, AWS Trainium/Marvell, Microsoft Maia) as the other structural entrant.
    AMD's share went from near zero in 2023 to ~5% by 2024 (a real, one-time step-up), but has been
    roughly flat since then, and AMD's own stated target is only to reach "double-digit" (10%+) share.
    AMD's accelerator growth is therefore primarily MARKET GROWTH, not share gain.

  growth_attribution: >
    BOTH, but dominated by MARKET GROWTH. AMD Instinct revenue rose from ~$0.4B (2023) to ~$5B (2024)
    to ~$9-10B (2025E), while the total AI accelerator market grew from ~$45B to ~$110B to ~$220B over
    the same period. That implies AMD's share was ~1% -> ~4.5% -> ~4.3%: a genuine share gain in
    2023-24 (0% to ~5% beachhead), then essentially FLAT share in 2025. The forward "share-gain to
    double digits" thesis that would justify premium valuation is a management target, not an evidenced
    trend, and faces a structural headwind from hyperscaler in-house ASICs (JPMorgan projects ASIC/XPU
    shipments to surpass GPUs by 2027).

  key_claims:
    - claim: "NVIDIA posted record FY2026 (ended Jan 25, 2026) total revenue of ~$215B, with gaming GPUs now only ~11.45% of revenue, implying data center of roughly ~$185-190B."
      source: "NVIDIA Q4/FY2026 earnings"
      source_type: filing
      publication_date: "2026-02-25"
      supporting_evidence: "Record $68.1B quarter and $215B fiscal year; gaming ~11.45%."
      confidence: high
      flags: []
    - claim: "AMD FY2025 revenue grew ~34% YoY to a record; Q4 2025 was AMD's first >$10B quarter; Data Center segment revenue grew ~39% YoY in Q4 2025 driven by MI350 GPU deployment and EPYC share gains."
      source: "AMD Q4/FY2025 earnings"
      source_type: filing
      publication_date: "2026-02-03"
      supporting_evidence: "Record 2025 revenue +34%; Q4 >$10B; Data Center +39% YoY."
      confidence: high
      flags: []
    - claim: "AMD's Data Center segment (Epyc + Instinct combined) was ~$5.4B in Q4 2025."
      source: "Finovian 'AMD Q4 2025 Earnings: $5.4B Data Center Explained'"
      source_type: third_party
      publication_date: "2026-02-03"
      supporting_evidence: "Q4 2025 data center segment revenue ~$5.4B."
      confidence: medium
      flags: []
    - claim: "IDC estimates NVIDIA holds ~71.2% and AMD ~5.8% of deployed cloud AI-accelerator nodes, remainder (~23%) split across Google/Huawei and other ASIC vendors."
      source: "IDC data via Chinese tech press"
      source_type: third_party
      publication_date: "2025"
      supporting_evidence: "Headlines: 'cloud accelerator deployment node share: NVIDIA ~72%, AMD 5.8%'."
      confidence: medium
      flags: [period_unclear]
      contradicts: null
    - claim: "In China, IDC shows NVIDIA's AI accelerator share fell to ~55% while domestic vendors (Huawei-led) reached ~41% in 2025."
      source: "IDC via MarketScreener"
      source_type: third_party
      publication_date: "2025"
      supporting_evidence: "IDC: NVIDIA China AI accelerator share 55%; domestic combined 41%."
      confidence: medium
      flags: []
    - claim: "AMD CEO Lisa Su (Nov 2025) characterized NVIDIA as monopolizing ~90% of the AI accelerator market and said AMD has a 'very clear path' to double-digit share; AMD targets ~35%+ annual revenue growth and sees the data-center chip market reaching $1 trillion."
      source: "CNBC / Anadolu (Analyst Day coverage)"
      source_type: management
      publication_date: "2025-11-11"
      supporting_evidence: "Lisa Su Analyst Day statements."
      confidence: high
      flags: [management_only]
    - claim: "AMD Instinct (data-center GPU) revenue was ~$5B in 2024 (up from ~$0.4B in 2023) and roughly ~$9-10B in 2025 (estimate)."
      source: "AMD earnings/guidance + analyst estimates"
      source_type: company_guidance
      publication_date: "2025-02-04"
      supporting_evidence: "AMD guided 2024 DC GPU >$5B and landed near that; 2025 inferred from segment split."
      confidence: medium
      flags: [unsupported, weak_source]
    - claim: "Custom ASICs are the fastest-growing segment: JPMorgan estimates the digital AI ASIC market reaches ~$60-70B by 2026 (40-50%+ CAGR); Broadcom ~80-85% of high-end ASIC, Marvell ~10-12%; ASIC/XPU unit shipments to surpass GPUs by 2027."
      source: "JPMorgan semiconductor research"
      source_type: sell_side
      publication_date: "2026"
      supporting_evidence: "ASIC market $60-70B by 2026; Broadcom AI $20B->$60B->$150B; 2027 ASIC outship GPUs."
      confidence: medium
      flags: [sell_side_forecast]
    - claim: "Data-center GPU shipments surged +145% QoQ in Q3 2025 (Jon Peddie Research)."
      source: "Jon Peddie Research"
      source_type: third_party
      publication_date: "2025-11-25"
      supporting_evidence: "Q3 2025 DC GPU shipments +145% QoQ vs PC GPU +2.5%."
      confidence: high
      flags: []

  key_assumptions:
    - { assumption: "'AI accelerator market' definition varies by source; NVIDIA ~70-90% and AMD ~4-6% depending on definition.", origin: inferred, confidence: high }
    - { assumption: "AMD 2025 Instinct-only revenue (~$9-10B) is estimated since AMD stopped cleanly disclosing a DC-GPU-only figure after 2024.", origin: inferred, confidence: medium }
    - { assumption: "Broadcom AI revenue and Google internal TPU deployments partly overlap, risking double-count in 'GPU + ASIC' sums.", origin: inferred, confidence: medium }
    - { assumption: "AMD's 'double-digit share' ambition makes share gain the swing factor in its 2026-29 thesis.", origin: analyst, confidence: medium }

  open_questions:
    - "Exact period/methodology of IDC 'NVIDIA 71.2% / AMD 5.8%' node-share figure not fully confirmed."
    - "AMD precise Instinct-only 2025 revenue not cleanly disclosed; ~$9-10B is an estimate."
    - "Whether AMD can reach double-digit share given the shift to hyperscaler in-house ASICs is unresolved — key risk to the share-gain leg."
    - "NVIDIA data-center FY2026 (~$185-190B) inferred, not directly confirmed."
    - "Global ex-China DC GPU unit share for AMD not captured."

  confidence: medium
```

## Director note

This is the pivotal finding for the thesis. It says the "share gain" leg is **not evidenced**:
AMD share ~5% and flat since the 2024 step-up from zero; growth is dominated by market growth.
The double-digit-share claim is `management_only`. This is high-importance and only medium-confidence
(the Instinct revenue and share methodology are estimates), so it is a strong candidate for a
recursive deep-dive — specifically the "design-win → realized revenue/share" conversion question.
