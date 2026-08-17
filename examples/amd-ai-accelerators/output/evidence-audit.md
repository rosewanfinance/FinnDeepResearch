# Evidence Audit — AMD / AI Accelerator Market

```yaml
claims:
  - claim: "AMD Data Center Q2 2026 = $6.7B, +54% YoY vs Q2 2025 base of $4,344M."
    source: "dc-segment-fundamentals"
    source_type: filing
    publication_date: "2026-08-05"
    supporting_evidence: "'Q2 2026 DC $6.7B (+54% Y/Y vs $4,344M Q2 2025).'"
    confidence: low
    flags: [unsupported, outdated]
    contradicts: [C2, C3]
  - claim: "AMD Data Center Q2 2025 = $6.09B (old segment definition)."
    source: "instinct-ramp-design-wins (AMD 2025 quarterly releases)"
    source_type: filing
    publication_date: "2025-08-05"
    supporting_evidence: "Q1 ~$4.15B, Q2 ~$6.09B, Q3 ~$7.4B, Q4 ~$8.4B."
    confidence: high
    flags: []
    contradicts: [C3]
  - claim: "AMD Data Center revenue 'more than doubled / +107% YoY' to ~$6.7B in Q2 2026."
    source: "AMD Q2 2026 earnings; Nasdaq/KuCoin/qz/Barchart"
    source_type: filing
    publication_date: "2026-08-04"
    supporting_evidence: "KuCoin 'DC up 107% YoY to $6.72B'; Nasdaq 'Doubled to $6.7B'."
    confidence: high
    flags: []
    contradicts: [C2]
  - claim: "AMD Data Center Q1 2026 = $5,380M, up 7% Q/Q (earnings slide)."
    source: "AMD Q1 2026 earnings slides (SEC fast-edgar)"
    source_type: filing
    publication_date: "2026-05-05"
    supporting_evidence: "Slide: 'Q1 2026 Segment Results … Data Center Up 7% … 5,380.'"
    confidence: high
    flags: []
    contradicts: null
  - claim: "AMD Data Center Q1 2026 = ~$6.5B (Finding A) or $5.8B (hyperscaler), both '+57%'."
    source: "dc-segment-fundamentals; hyperscaler-custom-silicon"
    source_type: filing
    publication_date: "2026-05-05"
    supporting_evidence: "Neither matches the primary slide $5,380M."
    confidence: low
    flags: [unsupported, outdated]
    contradicts: [C4]
  - claim: "AMD Instinct 2025 revenue ~$9-10B (up from ~$5B 2024, ~$0.4B 2023)."
    source: "accelerator-market-share"
    source_type: company_guidance
    publication_date: "2025-02-04"
    supporting_evidence: "2024 >$5B management-disclosed; 2025 inferred from segment split."
    confidence: low
    flags: [unsupported, weak_source, management_only]
    contradicts: null
  - claim: "AMD AI accelerator share ~4-6% and roughly FLAT since the 2024 step-up; growth primarily market growth, not share gain."
    source: "accelerator-market-share (IDC; inferred)"
    source_type: third_party
    publication_date: "2025"
    supporting_evidence: "Instinct $0.4B→$5B→$9-10B vs market $45B→$110B→$220B implies ~1%→~4.5%→~4.3%."
    confidence: medium
    flags: []
    contradicts: [C16]
  - claim: "Lisa Su: NVIDIA ~90% of AI accelerators; AMD 'very clear path' to double-digit share; ~35%+ revenue CAGR; $1T DC-chip market."
    source: "accelerator-market-share (CNBC/Anadolu)"
    source_type: management
    publication_date: "2025-11-11"
    supporting_evidence: "Analyst Day statements."
    confidence: high
    flags: [management_only]
    contradicts: null
  - claim: "NVIDIA retains ~80% of AI-accelerator market in 2026."
    source: "SiliconAnalysts"
    source_type: third_party
    publication_date: "2026"
    supporting_evidence: "~80%; other sources give ~71.2% (IDC nodes) and ~90% (Lisa Su)."
    confidence: low
    flags: [weak_source]
    contradicts: null
  - claim: "HSBC forecasts AMD 2026 AI-GPU revenue ~$19.8B, ~1/10th of NVIDIA's."
    source: "HSBC via 199it/siliconanalysts/UBS"
    source_type: sell_side
    publication_date: "2026"
    supporting_evidence: "Sell-side convergence."
    confidence: medium
    flags: [weak_source]
    contradicts: null
  - claim: "AMD ROCm 7.0 delivered ~3.5x AI performance and ~3.8x faster DeepSeek-R1 inference vs ROCm 6."
    source: "AMD ROCm 7.0 blog; Phoronix"
    source_type: primary_data
    publication_date: "2025"
    supporting_evidence: "Vendor-cited benchmarks; independent outlets relay vendor number."
    confidence: medium
    flags: [management_only]
    contradicts: null
  - claim: "ROCm advertises 'day-zero' support for leading open models with first-class PyTorch/JAX paths."
    source: "AMD Advancing AI keynote"
    source_type: management
    publication_date: "2025-2026"
    supporting_evidence: "Vendor marketing; conflicts with same finding's bf16 bugs / vLLM regression note."
    confidence: low
    flags: [management_only]
    contradicts: null
  - claim: "SemiAnalysis: AMD Meta/OpenAI warrants are performance-based; if AMD stock hits ~$600-700, counterparties' GPU capital cost approaches zero."
    source: "SemiAnalysis via KuCoin"
    source_type: news
    publication_date: "2026-07-20"
    supporting_evidence: "Meta 6GW; warrant dilution analysis."
    confidence: low
    flags: [weak_source, overreach]
    contradicts: null
  - claim: "NVIDIA has ~6M CUDA developers over 20 years."
    source: "NVIDIA GTC 2026; Stratrix ~5.9M"
    source_type: management
    publication_date: "2026-03"
    supporting_evidence: "NVIDIA GTC 2026 '20 years / 6M developers'."
    confidence: high
    flags: [management_only]
    contradicts: null
  - claim: "NVIDIA's production-inference software lead is WIDENING (vLLM >12k tok/s on MoE)."
    source: "SemiAnalysis via Wallstreetcn"
    source_type: third_party
    publication_date: "2026-07"
    supporting_evidence: "Multiple outlets report 'gap widens' framing."
    confidence: low
    flags: [weak_source]
    contradicts: null
  - claim: "JPMorgan: ASIC/XPU shipments exceed GPU in 2027 (12.5M vs 10.9M); Broadcom AI ~$20B→$60B+→$150B+."
    source: "JPMorgan"
    source_type: sell_side
    publication_date: "2026-05"
    supporting_evidence: "Forward unit mix and Broadcom pipeline."
    confidence: medium
    flags: [overreach]
    contradicts: null
  - claim: "Meta signed up to 6GW AMD deal (~$60-100B), AMD granting warrants up to 160M shares (AMD 8-K Feb 2026)."
    source: "AMD 8-K Feb 2026; Yahoo Finance; Moor Insights"
    source_type: filing
    publication_date: "2026-02"
    supporting_evidence: "SEC filing confirms scale + warrant structure."
    confidence: high
    flags: []
    contradicts: null
  - claim: "AMD guided DC +60% over 3-5 yrs, ~35% revenue CAGR; later 'roughly double again in 2027.'"
    source: "AMD Analyst Day; Q2 2026 call"
    source_type: management
    publication_date: "2025-11-13"
    supporting_evidence: "Forward guidance, not observed revenue."
    confidence: high
    flags: [management_only]
    contradicts: null
  - claim: "Digital AI ASIC market ~$60-70B in 2026 (40-50%+ CAGR); Broadcom ~80-85% high-end ASIC."
    source: "JPMorgan"
    source_type: sell_side
    publication_date: "2026-05"
    supporting_evidence: "Single-house forecast."
    confidence: medium
    flags: [overreach]
    contradicts: null

contradictions:
  - between: [C1, C2, C3]
    nature: "Irreconcilable Q2 2025 DC base: $4,344M (A) vs $6.09B (B) vs implied ~$3.2B restated (from +107%)."
    resolution: requires_investigation
    note: "Direction resolved: AMD re-segmented effective 2026 (Gaming→'Client and Gaming' confirmed in Q1 2026 10-Q; Q1 2026 slide 'Data Center $5,380M, up 7% Q/Q' incompatible with old-definition Q4 2025 ~$8.4B). $6.09B is correct OLD-definition; $4,344M erroneous; '+107%' uses a restated base not yet retrieved."
  - between: [C4, C5]
    nature: "Q1 2026 DC has three values: $5,380M (slide) vs ~$6.5B vs $5.8B."
    resolution: resolved_by
    note: "Primary slide shows $5,380M. Use $5,380M."
  - between: [C6, C16]
    nature: "Share trajectory conflict: FLAT since 2024 (market growth) vs GAINING via 2026 deals (share gain)."
    resolution: requires_investigation
    note: "Partially reconcilable on timing (2025 realized flat vs 2026-29 forward wins) and concentration (gains at ~4-5 hyperscalers only). But the growth-attribution verdicts directly conflict on the thesis's core driver. Needs realized 2026 Instinct revenue vs 2026 market."
  - between: [C8, NVIDIA-share range]
    nature: "NVIDIA share ~90% (mgmt) vs ~80% (SiliconAnalysts) vs ~71.2% (IDC nodes). Denominator inconsistency."
    resolution: resolved_by
    note: "Different denominators (revenue vs nodes; with/without ASICs; global vs ex-China)."
  - between: [C2, C3, 'accelerator sub-segment doubling']
    nature: "'Doubling' = total DC vs accelerator sub-segment only."
    resolution: requires_investigation
    note: "Unknown whether '+107%' is total DC (restated) or sub-segment; resolves with Q2 2026 slide/10-Q segment table."
  - between: [C12, C16]
    nature: "Meta/OpenAI deal value ambiguous: ~$60-100B headline vs near-zero-margin warrant economics."
    resolution: requires_investigation
    note: "Needs actual warrant strike/dilution terms from 8-K + realized ASPs."

audit_summary:
  strong_claims: 7
  weak_claims: 6
  flagged_claims: 13
  open_contradictions: 4
  confidence: low
```

## Director read

Evidence quality is **low**. The thesis has two legs, and both currently fail the weakest-link test:

- **Leg 1 (revenue base)** is quantitatively broken — the three findings cannot agree on the Q2 2025
  Data Center base, flipping Q2 2026 growth between +10%, +54%, and +107%. External verification
  resolves the *direction* (AMD re-segmented in 2026; Q1 2026 DC = $5,380M per primary slide; $6.09B is
  the correct old-definition Q2 2025 base; $4,344M is erroneous) but the exact restated comparable
  (~$3.2B) was not retrieved.
- **Leg 2 (share gain)** is asserted in both directions. The forward share-gain case rests on
  `management_only` targets ("double-digit share", "+60% DC over 3-5 yrs", "double again in 2027") and
  deal wins whose economic quality is contested (SemiAnalysis warrant dilution → near-zero-margin GPUs)
  and whose conversion to realized revenue is unproven as of Q2 2026.

The single highest-value action was to retrieve the primary Q2 2026 earnings slide/10-Q segment table
and the Meta warrant terms from the Feb 2026 8-K — that is exactly what the `amd-dc-revenue-reconciliation`
deep-dive is attempting (WebFetch is blocked network-wide, which is why these primary documents are hard
to reach).

Per the audit's own caution, the valuation stage should be built on ranges/scenarios and explicitly
flag the unresolved revenue-base and share-margin questions rather than pretending precision.
