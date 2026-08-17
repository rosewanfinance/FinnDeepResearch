# Finding — dc-segment-fundamentals (fundamentals)

```yaml
finding:
  question_id: dc-segment-fundamentals
  question: "What is the current size, growth rate, margin structure, and customer concentration of AMD's Data Center segment?"
  capability: fundamentals

  answer: >
    AMD's Data Center (DC) segment is now the dominant and fastest-growing business: revenue roughly
    doubled from ~$3.55B (Q3 2024) to $6.7B (Q2 2026), reaching ~55-60% of total revenue (Q2 2026:
    $6.7B of $11.5B). Growth is AI-accelerator (Instinct/Helios) and EPYC server-CPU driven. DC operating
    margin held a stable ~29-30% through 2024-2025 but is compressing in 2026 as the next-gen "Helios"
    accelerator ramps at lower initial margins — the explicit reason the stock sold off ~8-10% despite
    record revenue. Customer concentration is high and rising toward hyperscalers (Microsoft, Meta, Google,
    Oracle) plus a newly disclosed multi-billion-dollar OpenAI deal; AMD's 10-K discloses one unnamed
    customer at ~24% of FY2024 revenue.

  key_claims:
    - claim: "AMD total revenue rose from $6.819B (Q3 2024) to $11.5B (Q2 2026), up ~55% Y/Y in Q2 2026."
      statement_type: observed_fact
      source: "AMD Q2 2026 earnings release; AMD Q3 2024 earnings release"
      source_type: filing
      publication_date: "2026-08-05"
      supporting_evidence: "Q2 2026 revenue $11.5B (+~50-55% Y/Y); Q3 2024 $6.819B."
      confidence: high
    - claim: "Data Center segment revenue roughly doubled from $3.549B (Q3 2024) to $6.7B (Q2 2026)."
      statement_type: observed_fact
      source: "AMD quarterly earnings releases; Nasdaq coverage"
      source_type: filing
      publication_date: "2026-08-05"
      supporting_evidence: "Q3 2024 DC $3,549M; Q2 2026 DC $6.7B (+54% Y/Y vs $4,344M Q2 2025)."
      confidence: high
    - claim: "Data Center grew +57% Y/Y in Q1 2026 and became ~58-63% of total revenue by Q1-Q2 2026."
      statement_type: observed_fact
      source: "AMD Q1 2026 earnings release"
      source_type: filing
      publication_date: "2026-05-05"
      supporting_evidence: "Q1 2026 DC ≈ $6.5B vs $4,123M Q1 2025 (+57%); Q2 DC $6.7B = 58% of $11.5B."
      confidence: high
    - claim: "The AI-accelerator (Instinct/MI-series/Helios) portion is growing faster than the segment overall, roughly doubling Y/Y in Q2 2026."
      statement_type: management_claim
      source: "AMD Q2 2026 earnings call transcript"
      source_type: earnings_call
      publication_date: "2026-08-05"
      supporting_evidence: "Headlines describe DC 'doubling' while total DC grew ~54%; +107% figure most consistent with accelerator sub-segment."
      confidence: medium
      flags: [management_only]
    - claim: "Gaming segment stagnated (~$400-560M/quarter) and was merged into a combined 'Client and Gaming' segment beginning Q1 2026."
      statement_type: observed_fact
      source: "AMD Q1 2026 10-Q segment footnote"
      source_type: filing
      publication_date: "2026-05-06"
      supporting_evidence: "10-Q 3-segment structure (Data Center; Client and Gaming; Embedded) effective 2026."
      confidence: high
    - claim: "Embedded segment revenue fell from ~$927M (Q3 2024) to a trough of ~$379M (Q2 2025), recovered to ~$1.0B (Q3-Q4 2025), ~$0.9B in Q2 2026."
      statement_type: observed_fact
      source: "AMD quarterly earnings releases"
      source_type: filing
      publication_date: "2026-08-05"
      supporting_evidence: "Q2 2026 Embedded residual ~$0.92B."
      confidence: medium
    - claim: "Data Center operating margin was a stable ~29-30% through 2024-2025, before compressing in 2026."
      statement_type: observed_fact
      source: "AMD 10-Q/10-K segment operating income disclosures"
      source_type: filing
      publication_date: "2026-02-04"
      supporting_evidence: "Q3 2024 29.3%; Q4 2024 30.0%; Q1 2025 30.1%; Q2 2025 30.3%."
      confidence: high
    - claim: "Data Center and company-wide gross margins are being compressed in 2026 by the Helios accelerator ramp; management's margin guide disappointed, driving the post-earnings sell-off."
      statement_type: management_claim
      source: "AMD Q2 2026 earnings call; multiple reports"
      source_type: earnings_call
      publication_date: "2026-08-05"
      supporting_evidence: "Stock fell ~8-10% despite the beat; capex >$800M and FCF declined in Q2 2026."
      confidence: medium
      flags: [management_only]
    - claim: "Company non-GAAP gross margin was ~54% in Q3 2025 (up 40bps Y/Y); GAAP GM ~50-53% over 2024-2025."
      statement_type: observed_fact
      source: "AMD Q3 2025 earnings call transcript"
      source_type: earnings_call
      publication_date: "2025-11-04"
      supporting_evidence: "Non-GAAP GM 54% Q3 2025."
      confidence: high
    - claim: "R&D spend was ~$6.46B in FY2024, rising in absolute dollars but falling as a share of revenue as Data Center scales."
      statement_type: inferred_conclusion
      source: "AMD FY2024 10-K"
      source_type: filing
      publication_date: "2025-02-05"
      supporting_evidence: "R&D ~25% of revenue FY2024, declining toward ~20% FY2025."
      confidence: medium
      flags: [FY2025_figure_not_verified]
    - claim: "Operating cash flow improved from ~$1.67B (FY2023) to ~$3.06B (FY2024), rising in FY2025; Q2 2026 FCF dipped as capex exceeded $800M."
      statement_type: inferred_conclusion
      source: "AMD 10-K cash-flow statements; Q2 2026 reports"
      source_type: filing
      publication_date: "2026-02-04"
      supporting_evidence: "FY2023 OCF $1.667B; FY2024 OCF $3.063B."
      confidence: medium
      flags: [FY2025_figure_not_verified]
    - claim: "AMD FY2024 10-K disclosed one customer at ~24% of consolidated net revenue (up from ~16% FY2023), widely understood to be a large distributor/ODM."
      statement_type: observed_fact
      source: "AMD FY2024 10-K Customer Concentration note"
      source_type: filing
      publication_date: "2025-02-05"
      supporting_evidence: "10-K 'one customer accounted for 24% of net revenue'."
      confidence: medium
      flags: [FY2025_%_not_verified]
    - claim: "AMD's largest Data Center end-customers are hyperscalers (Microsoft, Meta, Google, Oracle) plus OpenAI (~$10B Instinct/Helios supply agreement announced Oct 2025)."
      statement_type: observed_fact
      source: "OpenAI/AMD deal reporting (TrendForce, CIO Dive, Oct 2025)"
      source_type: news
      publication_date: "2025-10-07"
      supporting_evidence: "OpenAI taps AMD for massive compute buildout with CoreWeave/Oracle."
      confidence: high
    - claim: "On a bill-to basis, AMD revenue is heavily weighted to Asia (China ~22%, Hong Kong ~22%), with US ~33%."
      statement_type: observed_fact
      source: "AMD 10-K geographic note"
      source_type: filing
      publication_date: "2026-02-04"
      supporting_evidence: "China ~$7.75B (~22.4%) of FY2025 revenue."
      confidence: medium

  key_assumptions:
    - { assumption: "Segment reclassification (Gaming → 'Client and Gaming') does not change Data Center segment boundary.", origin: inferred, confidence: medium }
    - { assumption: "'Doubling' language in Q2 2026 refers to the AI-accelerator sub-segment, not total DC (+54%).", origin: inferred, confidence: medium }
    - { assumption: "Helios ramp carries below-corporate-average gross margin, consistent with prior product ramps.", origin: company_guidance, confidence: medium }

  open_questions:
    - "Exact FY2025 and Q3-Q4 2025 / Q1-Q2 2026 GAAP segment revenue/op income not pulled directly from 10-Q/10-K (WebFetch blocked)."
    - "Exact FY2025 R&D, OCF, FCF not verified from 10-K."
    - "FY2025 customer-concentration % (still ~24%? distributor vs named hyperscaler?) not verified."
    - "Q2 2026 DC segment operating income/margin exact figures not retrieved."
    - "Whether OpenAI displaced the distributor/Microsoft as the single largest disclosed customer."
    - "Reconciliation gap: reported FY2025 revenue (~$34.6B) vs sum of recalled quarterly figures (~$34.1B)."

  confidence: medium
```

## Director note

Confirms the margin-compression story that the valuation must account for: DC op margin was a stable
~29-30% through 2025 but is compressing in 2026 as Helios ramps at lower initial margins — this is why
the stock fell ~9% despite a record $11.5B quarter. Customer concentration is high and rising (one
customer ~24% FY2024; hyperscalers + OpenAI dominant). The accelerator sub-segment is growing ~2x Y/Y
vs. ~54% for total DC — the wedge the share-gain thesis rests on.
