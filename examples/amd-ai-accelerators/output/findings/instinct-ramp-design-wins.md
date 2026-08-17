# Finding — instinct-ramp-design-wins (fundamentals)

```yaml
finding:
  question_id: instinct-ramp-design-wins
  question: "How fast is AMD's Instinct accelerator revenue ramping, and what is the evidence that announced design wins are converting into realized revenue?"
  capability: fundamentals

  answer: >
    AMD's Instinct accelerator revenue has ramped very fast in absolute terms — from ~zero at launch
    (Q4 2023) to >$5B of data-center-GPU revenue in 2024 and an estimated ~$10B+ in 2025. Early design
    wins (Meta, Microsoft, Oracle) demonstrably converted into realized revenue. However, the two largest
    announced wins — OpenAI (6GW, "tens of billions," Oct 2025) and Anthropic (~$5B AMD investment +
    MI450 supply, 2026) — are 2026–2029 commitments that had NOT yet shown up in realized revenue as of
    Q2 2026. Separately, 2026 segment reporting appears to have been re-cut, which is not reconcilable
    against the 2025 base without the primary filing — so the exact quarter-over-quarter Instinct
    trajectory in 2026 cannot be confirmed here. Net: the ramp is real but the mega-deal conversion is
    still unproven.

  key_claims:
    - claim: "AMD data center GPU (Instinct) revenue exceeded $5B in calendar 2024."
      type: management_claim
      source: "AMD Q4 2024 earnings call"
      source_type: earnings_call
      publication_date: "2025-02-04"
      supporting_evidence: "Lisa Su disclosed 2024 DC GPU revenue >$5B."
      confidence: high
      flags: [management_only]
    - claim: "AMD Data Center segment revenue (EPYC + Instinct) was $12.58B in FY2024, up 94% YoY."
      type: observed_fact
      source: "AMD FY2024 10-K / Q4 2024 release"
      source_type: filing
      publication_date: "2025-02-04"
      supporting_evidence: "Q1 $2.34B, Q2 $2.83B, Q3 $3.55B, Q4 $3.86B."
      confidence: high
    - claim: "AMD Data Center segment roughly doubled in 2025 to ~$26B (Q1 ~$4.15B, Q2 ~$6.09B, Q3 ~$7.4B, Q4 ~$8.4B)."
      type: observed_fact
      source: "AMD 2025 quarterly releases; FY2025 10-K"
      source_type: filing
      publication_date: "2026-02-04"
      supporting_evidence: "Quarterly figures from press releases; FY2025 revenue +34% to ~$34.5B."
      confidence: medium
      flags: [needs_verification]
    - claim: "AMD total revenue ~$34.5B FY2025 (+34%), net income ~$2.5B, FCF ~$2.1B."
      type: observed_fact
      source: "AMD Q4/FY2025 earnings"
      source_type: earnings_call
      publication_date: "2026-02-04"
      supporting_evidence: "2025 revenue +34%; NI $2.5B; FCF $2.1B."
      confidence: high
    - claim: "AMD Q1 2026 total revenue $10.25B (+38%), Data Center segment +57% YoY; slide shows Data Center $5,380M."
      type: observed_fact
      source: "AMD Q1 2026 earnings"
      source_type: earnings_call
      publication_date: "2026-05-05"
      supporting_evidence: "Total +38%; DC +57%; slide 'Data Center 5,380'."
      confidence: high
      flags: []
    - claim: "AMD Q2 2026 total revenue record ~$11.5B; Data Center ~$6.7B, described by media as 'more than doubled YoY.'"
      type: observed_fact
      source: "AMD Q2 2026 earnings"
      source_type: earnings_call
      publication_date: "2026-08-04"
      supporting_evidence: "Total ~$11.5B; DC ~$6.7B vs 'more than doubled' headlines."
      confidence: medium
      flags: [needs_verification]
    - claim: "AMD Q2 2026 net income ~$2.3B; capex roughly tripled YoY; $5B bond sale to fund AI expansion."
      type: observed_fact
      source: "nextapple / ofweek"
      source_type: earnings_call
      publication_date: "2026-08-05"
      supporting_evidence: "Q2 NI ~$2.3B; capex tripled; $5B bond."
      confidence: medium
    - claim: "AMD raised, then exceeded, its own 2024 DC GPU guidance (~$2B → $3.5B → $4.5B → $5B+, ultimately exceeded $5B)."
      type: management_claim
      source: "AMD earnings calls through 2024"
      source_type: earnings_call
      publication_date: "2024-01-30 to 2025-02-04"
      supporting_evidence: "Guidance raised three times in 2024, then exceeded."
      confidence: high
      flags: [management_only]
    - claim: "At Nov 2025 Financial Analyst Day, AMD projected Data Center revenue to grow ~60% over 3–5 years and company revenue CAGR of ~35%."
      type: management_claim
      source: "AMD Financial Analyst Day (Nov 12, 2025)"
      source_type: management
      publication_date: "2025-11-13"
      supporting_evidence: "'data center revenue will jump 60% over next 3-5 years'; '35% revenue CAGR.'"
      confidence: high
      flags: [management_only]
    - claim: "OpenAI agreed Oct 2025 to a multi-year Instinct supply deal worth 'tens of billions' covering ~6GW of compute capacity."
      type: observed_fact
      source: "TechCrunch / CNBC TV18"
      source_type: news
      publication_date: "2025-10-06"
      supporting_evidence: "'AMD to supply 6GW of compute capacity to OpenAI in chip deal worth tens of billions.'"
      confidence: high
      flags: []
    - claim: "Anthropic signed an AI-chip supply agreement with AMD (AMD investing up to $5B in Anthropic); MI450 rumored part; Claude adapted to AMD hardware in ~2 days."
      type: observed_fact
      source: "stcn.com / edgen.tech"
      source_type: news
      publication_date: "2026-07-24"
      supporting_evidence: "'AMD will invest up to $5B in Anthropic'; 'Claude adapts AMD chips in 2 days.'"
      confidence: medium
      flags: [weak_source]
    - claim: "Meta, Microsoft, Oracle converted MI300X design wins into realized deployments in 2024–2025."
      type: inferred_conclusion
      source: "Company announcements + AMD DC GPU revenue disclosures"
      source_type: news
      publication_date: "2024-2025"
      supporting_evidence: "DC GPU revenue grew ~$400M (Q4'23) to >$5B (2024), only explainable by named hyperscaler deployments."
      confidence: medium
      flags: []
    - claim: "OpenAI and Anthropic mega-deals had not yet contributed materially to realized revenue as of Q2 2026."
      type: inferred_conclusion
      source: "Deal timing vs Q2 2026 results"
      source_type: news
      publication_date: "2026-08-04"
      supporting_evidence: "Deals post-date reported quarters; multi-year ramps."
      confidence: medium
      flags: []
    - claim: "AMD's data center growth is decelerating in 2026 (Q1'26 +57%, Q2'26 ~$6.7B vs 2025's >100% YoY quarters)."
      type: inferred_conclusion
      source: "Q1/Q2 2026 results; market reaction"
      source_type: news
      publication_date: "2026-08-05"
      supporting_evidence: "Multiple outlets note deceleration and post-beat sell-offs."
      confidence: medium
      flags: [overreach]
    - claim: "AMD does not disclose a clean 'Instinct-only' revenue line after 2024; data center GPU revenue is folded into the Data Center segment."
      type: inferred_conclusion
      source: "AMD financial disclosures"
      source_type: filing
      publication_date: "2026-02-04"
      supporting_evidence: "2025 10-K reports Data Center, Client, Gaming, Embedded segments without separate Instinct line."
      confidence: high

  key_assumptions:
    - { assumption: "FY2025 Instinct/DC-GPU revenue ~$10B (roughly doubling from >$5B in 2024).", origin: inferred, confidence: low }
    - { assumption: "AMD re-segmented reporting effective 2026 (splitting Instinct out of 'Data Center'), explaining the $5.38B/$6.7B figures vs 'doubled' headlines.", origin: inferred, confidence: low }
    - { assumption: "OpenAI (6GW) and Anthropic ($5B + MI450) deals convert over 2026–2029 but not yet meaningfully.", origin: analyst, confidence: medium }

  open_questions:
    - "Exact FY2025 Data Center segment revenue and FY2025 Instinct/DC-GPU revenue not independently confirmed."
    - "Did AMD re-segment in 2026? Q1'26 'Data Center $5,380M' and Q2'26 '~$6.7B' are irreconcilable with 'more than doubled YoY' against a $6.09B Q2'25 base unless re-segmentation occurred."
    - "Precise quarterly Instinct revenue trajectory for Q1'26/Q2'26 not extractable."
    - "How much OpenAI/Anthropic revenue was recognized through Q2 2026?"
    - "Q3 2026 management guidance for Data Center / Instinct not retrieved."
    - "China MI308 dynamics ($360M inventory release Q4'25, ~$100M Q1'26 sales) suggest export-control volatility, unquantified."

  confidence: low
```

## Director note

**Low confidence.** Two load-bearing open questions: (1) the exact FY2025/H1-2026 Data Center revenue
base is uncertain because the 2026 re-segmentation is unconfirmed; (2) the 2025–26 mega-deals (OpenAI
6GW, Anthropic ~$5B) have not yet converted to realized revenue. The design-win → revenue conversion
for the 2023–24 cohort (Meta/Microsoft/Oracle) is proven; the 2026–29 cohort is not.
