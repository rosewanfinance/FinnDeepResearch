# Finding — amd-dc-revenue-reconciliation (fundamentals, recursive deep-dive)

```yaml
finding:
  question_id: amd-dc-revenue-reconciliation
  question: "What is AMD's exact Data Center segment revenue by quarter from Q1 2025 through Q2 2026, did AMD re-segment its reporting in 2026, and is the AI-accelerator (Instinct) revenue accelerating or decelerating?"
  capability: fundamentals

  answer: >
    NEITHER prior finding was correct as a whole. Correct Data Center ("DC" = EPYC server CPU +
    Instinct accelerator, definition UNCHANGED through Q2 2026) quarterly revenue: Q1'25 $4.1B,
    Q2'25 $3.2B, Q3'25 $4.3B, Q4'25 $5.0B, Q1'26 $5.38B, Q2'26 $6.7B — FY2025 total $16.6B, NOT
    ~$26B. Finding B's 2025 series was overstated by ~50%. Finding A's Q1'25 was right but its Q2'25
    ($4,344M) was wrong (actual $3.2B, a sequential DROP caused by the US China-export-control "chips
    curb"), and its 2026 YoY claims (+57%/+54%) were wrong (actual +32%/+107%). AMD did re-segment, but
    by merging Client+Gaming into "Client and Gaming" effective Q1 2025 (FY2025) — NOT a 2026
    Instinct/Data Center split. Instinct decelerated hard into Q2 2025 and is now re-accelerating: Q2
    2026 DC "more than doubled" (+107% YoY) — but that doubling is the WHOLE segment against a depressed
    Q2 2025 base.

  key_claims:
    - claim: "AMD FY2025 Data Center segment revenue was a record $16.6B, up 32% YoY."
      source: "AMD FY2025 10-K (accession 0000002488-26-000014)"
      source_type: filing
      publication_date: "2026-02-04"
      supporting_evidence: "10-K: 'Data Center segment revenue was a record $16.6 billion, up 32%.'"
      confidence: high
    - claim: "AMD Q2 2025 Data Center net revenue was $3.2B, up 14% YoY."
      source: "AMD Q2 2025 10-Q (accession 0000002488-25-000108)"
      source_type: filing
      publication_date: "2025-08"
      supporting_evidence: "'Data Center net revenue of $3.2 billion ... increased by 14%.'"
      confidence: high
    - claim: "AMD Q3 2025 Data Center net revenue was $4.3B, up 22% YoY."
      source: "AMD Q3 2025 10-Q (accession 0000002488-25-000166)"
      source_type: filing
      publication_date: "2025-11-04"
      supporting_evidence: "'Data Center net revenue of $4.3 billion ... increased by 22%.'"
      confidence: high
    - claim: "AMD Q1 2026 Data Center revenue was $5,380M, up 7% QoQ."
      source: "AMD Q1 2026 earnings slides"
      source_type: filing
      publication_date: "2026-05-05"
      supporting_evidence: "Slide 'Q1 2026 Segment Results ... Data Center Up 7% ... 5,380' (Q/Q column → Q4'25 ≈ $5.03B)."
      confidence: high
    - claim: "AMD Q2 2026 Data Center revenue was $6.7B, up 107% YoY ('more than doubled')."
      source: "AMD Q2 2026 press release; iresearch/nasdaq/qz"
      source_type: filing
      publication_date: "2026-08-05"
      supporting_evidence: "'Data Center revenue +107% YoY'; $3.2B × 2.07 = $6.62B."
      confidence: high
    - claim: "AMD combined Client and Gaming into one 'Client and Gaming' segment effective fiscal year 2025 (Q1 2025), not 2026."
      source: "AMD Q1 2025 10-Q (accession 0000002488-25-000047)"
      source_type: filing
      publication_date: "2025-05-06"
      supporting_evidence: "'Beginning with the fiscal year ending December 27, 2025, we combined the Client and Gaming segments...'"
      confidence: high
    - claim: "AMD did NOT split Instinct out of Data Center in 2026 — Data Center still holds EPYC + Instinct through Q2 2026."
      source: "AMD Q1/Q2 2026 10-Q segment notes; Q2 2026 transcript"
      source_type: filing
      publication_date: "2026-08-05"
      supporting_evidence: "Three segments only; +107% YoY comparable to Q2 2025 $3.2B (same definition)."
      confidence: medium
      flags: [management_only]
    - claim: "AMD Data Center operating margin compressed in 2025 (not 'stable ~29-30%')."
      source: "AMD Q3 2025 10-Q (amd-20250927.htm)"
      source_type: filing
      publication_date: "2025-11-04"
      supporting_evidence: "'Data Center operating income was $1.9B for 9M 2025 vs $2.3B [9M 2024]' — income FELL while revenue rose (~16% vs ~27% margin)."
      confidence: high
    - claim: "AMD stopped cleanly disclosing standalone Instinct/DC-GPU revenue after FY2024 (>$5B); no clean FY2025/H1 2026 Instinct total disclosed."
      source: "AMD Q4 2025 8-K/10-K; absence of standalone figure"
      source_type: filing
      publication_date: "2026-02-03"
      supporting_evidence: "Only Instinct item for FY2025: ~$360M release of reserved MI308 inventory in Q4'25."
      confidence: medium
      flags: [unsupported]

  key_assumptions:
    - { assumption: "Q1 2026 slide 'Up 7%' is QoQ (vs Q4'25).", origin: inferred, confidence: high }
    - { assumption: "Q4 2025 DC ≈ $5.03B and Q1 2025 ≈ $4.07B, derived from FY2025 $16.6B minus Q2 $3.2B/Q3 $4.3B and the +7% QoQ anchor.", origin: inferred, confidence: high }
    - { assumption: "Media '+57%' DC growth for Q1 2026 is an error (arithmetically inconsistent with FY2025 $16.6B and +7% QoQ).", origin: inferred, confidence: medium }

  open_questions:
    - "Exact Q1 2025 DC dollar + YoY% not directly confirmed (derived ~$4.07-4.12B)."
    - "Exact Q4 2025 DC derived ~$5.0B (one low-quality source said $5.4B, inconsistent)."
    - "Exact Q2 2026 DC dollar in millions not retrieved (only $6.7B +107%)."
    - "Q3 2026 / FY2026 DC guidance exact figures not confirmed (only that Q3 total revenue guided above Street; shares fell ~9-10% on 'lofty expectations')."
    - "Standalone Instinct FY2025/H1 2026 not disclosed (only the $360M Q4'25 MI308 reserve release)."
    - "Whether AMD splits DC into a separate 'AI' segment in a future quarter (2027+)."

  confidence: high
```

## Reconciliation verdict (correct figures)

| Quarter | Data Center revenue | YoY | Prior findings |
|---|---|---|---|
| Q1 2025 | ~$4.1B | ~+77% | A/B ~$4.1B ✓ |
| Q2 2025 | **$3.2B** | **+14%** | A $4,344M ✗; B $6.09B ✗ |
| Q3 2025 | **$4.3B** | **+22%** | B $7.4B ✗ |
| Q4 2025 | ~$5.0B | ~+29% | B $8.4B ✗ |
| FY2025 | **$16.6B** | **+32%** | B "≈$26B" ✗ |
| Q1 2026 | **$5,380M** | ~+32% (not +57%) | A +57%/$6.5B ✗ |
| Q2 2026 | **$6.7B** | **+107%** | A +54% ✗ |

Re-segmentation = Client+Gaming merged effective Q1 2025. No Instinct split.

## Director note — thesis-relevant corrections

1. **The "+107% / doubling" in Q2 2026 is flattered by a depressed base.** Q2 2025 DC was $3.2B, hit by
   the US China export-control "chips curb" and MI325X softness. So the headline "doubling" partly
   reflects a weak comparison, not pure organic acceleration.
2. **Margin compression began in 2025, not 2026.** 9M-2025 DC operating income *fell* YoY while revenue
   rose — the "stable ~30% margin" claim was wrong. This strengthens the margin-compression bear point.
3. **FY2025 DC = $16.6B, not ~$26B** — the revenue base the share-gain thesis builds on is smaller than
   the instinct-ramp finding implied, which matters for the 2026→2029 growth arithmetic.
4. **Instinct is accelerating** (+22% → +29% → +32% → +107%), but the acceleration is partly base-effect.
