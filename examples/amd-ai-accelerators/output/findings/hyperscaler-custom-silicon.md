# Finding — hyperscaler-custom-silicon (industry_competitive)

```yaml
finding:
  question_id: hyperscaler-custom-silicon
  question: "How are hyperscalers allocating AI accelerator capex across NVIDIA, AMD, and in-house custom silicon (TPU/Trainium/Maia), and is custom silicon a growing threat to AMD's addressable opportunity?"
  capability: industry_competitive

  answer: >
    Hyperscaler AI capex is at record scale (TrendForce pegs nine largest CSPs at ~$830B in 2026; the
    big four ~$725B, +77% YoY). The accelerator wallet is split three ways: NVIDIA keeps the dominant
    merchant-GPU share (~80% of AI accelerators), AMD is winning the "second merchant source" role (Meta
    6GW / ~$60–100B, OpenAI, Microsoft Helios rack-scale), and in-house ASICs (Google TPU, AWS Trainium,
    Microsoft Maia, Meta MTIA/Iris, OpenAI XPU) ramp fastest of all — JPMorgan forecasts digital AI ASIC
    revenue ~$60–70B in 2026 (40–50%+ CAGR) and ASIC/XPU unit shipments exceeding GPUs in 2027 (12.5M vs
    10.9M). Custom silicon IS a growing structural threat to AMD's addressable opportunity, but in
    2026–2027 it primarily erodes NVIDIA's share and simultaneously pulls AMD in (every hyperscaler
    diversifying away from NVIDIA buys AMD as the merchant alternative while it ramps its own ASIC). The
    decisive risk: AMD's three largest buyers are all simultaneously building their own silicon, so AMD's
    merchant TAM is bounded above by NVIDIA and below by in-house ASICs.

  growth_attribution: >
    BOTH market growth and market-share gain — but the share-gain component is the larger swing factor on
    a low base. AMD Data Center doubled YoY in Q2 2026 ($6.7B) against a hyperscaler capex base growing
    ~50–77% YoY (market-growth tailwind), while AMD went from negligible share to high-single-digit share
    by winning second-source deals (Meta, OpenAI, Microsoft) NVIDIA did not get (share-gain driver).
    Custom silicon grows faster than either merchant vendor, but near-term displaces NVIDIA first and
    pulls AMD along as the merchant diversifier.

  key_claims:
    - claim: "Hyperscaler AI capex at record scale in 2026: nine major CSPs ~$830B (TrendForce); big four ~$725B, +77% YoY."
      source: "TrendForce / Yahoo Finance / Futurum"
      source_type: third_party
      publication_date: "2026-05-06"
      supporting_evidence: "TrendForce raised nine-CSP capex to $830B; Yahoo cites $725B +77%."
      confidence: high
      flags: []
    - claim: "Digital AI ASIC market reaches ~$60–70B in 2026, growing 40–50%+ annually; Broadcom ~80–85% high-end ASIC, Marvell ~10–12%."
      source: "JPMorgan"
      source_type: sell_side
      publication_date: "2026-05"
      supporting_evidence: "JPMorgan AI ASIC forecast."
      confidence: medium
      flags: [management_only, overreach]
    - claim: "Broadcom AI revenue scales ~$20B (FY25) → $60B+ (FY26) → $150B+ (FY27), on Google TPU, Meta MTIA, ByteDance, OpenAI XPU, SoftBank/Arm, Anthropic."
      source: "JPMorgan"
      source_type: sell_side
      publication_date: "2026-05"
      supporting_evidence: "Broadcom pipeline enumeration."
      confidence: medium
      flags: [overreach]
    - claim: "Marvell data-center revenue scales ~$6.1B (2025) → ~$9.3B (2026) → ~$14.6B (2027), on Amazon Trainium 3/4 and Microsoft Maia."
      source: "JPMorgan"
      source_type: sell_side
      publication_date: "2026-05"
      supporting_evidence: "Marvell drivers enumerated."
      confidence: medium
      flags: [overreach]
    - claim: "ASIC/XPU unit shipments exceed GPU shipments in 2027: 23.3M total, 10.9M GPUs (47%) vs 12.5M ASIC/XPU (53%)."
      source: "JPMorgan"
      source_type: sell_side
      publication_date: "2026-05"
      supporting_evidence: "JPMorgan 2027 unit mix forecast."
      confidence: medium
      flags: [overreach]
    - claim: "Google TPU v7 'Ironwood' generally available; TPU v8 splits Broadcom training (8t) + MediaTek/Marvell inference (8i); Anthropic signed ~$21B TPU deal with Google/Broadcom."
      source: "The Next Web / wccftech"
      source_type: news
      publication_date: "2026-04"
      supporting_evidence: "Ironwood GA; TPUv8 bifurcation; Anthropic $21B deal."
      confidence: high
      flags: []
    - claim: "AWS Trainium 3 GA December 2025 (TSMC 3nm, 144GB HBM3E), claimed >50% lower cost vs comparable GPUs; Amazon spending ~$200B on AI data centers in 2026; Trainium 4 in development."
      source: "GadgetsNow / Motley Fool"
      source_type: news
      publication_date: "2026-02-19"
      supporting_evidence: "Trainium 3 GA specs; Amazon $200B capex."
      confidence: high
      flags: []
    - claim: "Microsoft deploying Broadcom-designed Maia 200 in Azure, in talks to supply Anthropic — while simultaneously buying AMD's Helios rack-scale system."
      source: "Silicon UK / CNBC TV18"
      source_type: news
      publication_date: "2026-05-22"
      supporting_evidence: "Maia 200 deployment; Anthropic talks; Microsoft joins AMD Helios."
      confidence: high
      flags: []
    - claim: "Meta's custom MTIA successor 'Iris' (Broadcom-designed) passes testing, enters production Sept 2026, as Meta targets doubling AI compute to 14GW — while committing ~6GW of AMD Instinct GPUs."
      source: "The Standard / ITHome"
      source_type: news
      publication_date: "2026-07-09"
      supporting_evidence: "Iris production Sept 2026; 14GW target; 6GW AMD deal."
      confidence: high
      flags: []
    - claim: "AMD Data Center revenue: $5.8B Q1 2026 (+57% YoY), $6.7B Q2 2026 (roughly doubled YoY); total Q2 revenue $11.5B record (+50%); data center ~58% of revenue; management guides data-center to roughly double again in 2027."
      source: "AMD Q2 2026 earnings"
      source_type: earnings_call
      publication_date: "2026-08-05"
      supporting_evidence: "Q2 DC $6.7B doubled; record $11.5B; 58% of revenue; 2027 doubling guidance."
      confidence: high
      flags: []
    - claim: "AMD's largest AI buyers are Meta (~6GW / ~$60–100B multi-year), OpenAI, Microsoft (Helios), plus Oracle; SemiAnalysis reports AMD signed performance-based WARRANT agreements with Meta and OpenAI covering up to 6GW, such that if AMD's stock reaches ~$600–700 the counterparties' GPU capital cost could approach zero."
      source: "SemiAnalysis via KuCoin / Techmonitor / Extremetech"
      source_type: news
      publication_date: "2026-07-20"
      supporting_evidence: "Meta 6GW deal ($60–100B); OpenAI+Meta ~12GW; warrant analysis."
      confidence: medium
      flags: [weak_source]
    - claim: "AMD Helios rack-scale system (MI400-based, ~$5.25M/rack) priced ~40% above NVIDIA Rubin yet still won Microsoft's full-stack order, shipping year-end 2026."
      source: "tech-insider / MoneyDJ"
      source_type: news
      publication_date: "2026-07-21"
      supporting_evidence: "Helios $5.25M rack; ~40% above Rubin; Microsoft adoption."
      confidence: medium
      flags: []
    - claim: "NVIDIA retains ~80% of AI accelerator market share in 2026."
      source: "SiliconAnalysts"
      source_type: third_party
      publication_date: "2026"
      supporting_evidence: "~80% attributed to NVIDIA."
      confidence: medium
      flags: [weak_source]
    - claim: "AMD at rough 1:1 parity with NVIDIA among neoclouds splitting GPU orders."
      source: "Fierce Network (VAST Data)"
      source_type: news
      publication_date: "2026"
      supporting_evidence: "Neoclouds splitting NVIDIA/AMD ~1:1."
      confidence: low
      flags: [weak_source, overreach]

  key_assumptions:
    - { assumption: "Hyperscaler AI capex keeps growing through 2026–2027 rather than a digestion year.", origin: industry_forecast, confidence: medium }
    - { assumption: "JPMorgan ASIC-overtakes-GPU-by-2027 forecast is directionally correct.", origin: analyst, confidence: medium }
    - { assumption: "AMD's share gains are sticky — Meta/OpenAI/Microsoft treat AMD as a durable second source, not a bridge until their ASICs mature.", origin: inferred, confidence: low }
    - { assumption: "Custom silicon erodes NVIDIA first and pulls AMD along near-term.", origin: inferred, confidence: medium }

  open_questions:
    - "No single authoritative dollar split of hyperscaler AI-accelerator capex across NVIDIA/AMD/custom silicon for 2026; cleanest public figure is JPMorgan's 2027 unit mix."
    - "AMD's exact customer concentration unconfirmed from primary filings (10-Q >10% customer disclosures not retrievable)."
    - "True economic value of AMD's Meta deal ambiguous ($60B vs $100B); SemiAnalysis claims warrants could make GPUs near-free to Meta/OpenAI if AMD stock rallies — implying share gain may be low/zero margin."
    - "Execution risk on custom-silicon ramps (Trainium 3/4, Meta Iris, Maia 200 volumes)."
    - "Whether hyperscalers KEEP second-sourcing merchant GPUs once ASICs mature (~2028+) — determines if AMD's 2026–2027 wins are durable."

  confidence: medium
```

## Director note

Three-way split confirmed: NVIDIA ~80%, custom silicon fastest-growing (ASIC > GPU units by 2027),
AMD winning the merchant "second source" role (Meta/OpenAI/Microsoft). Two valuation-critical facts
surfaced here: (1) AMD stock fell ~9% post-Q2-earnings "because of what growth costs" — i.e., margin/
dilution concerns; (2) SemiAnalysis reports warrant-laden Meta/OpenAI deals that could make the GPUs
near-zero-cost to the buyers if AMD stock rallies, implying the share wins may be low-margin. Both are
high-importance and must feed the valuation and bear-case stages.
