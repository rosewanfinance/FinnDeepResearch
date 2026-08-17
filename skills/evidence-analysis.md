# Skill: Evidence & Contradiction Analysis

## Purpose

Evaluate the *quality* of research evidence. The goal is a **defensible** conclusion, not a
convincing one.

## Inputs

- The assembled `key_claims` from one or more findings (fundamental / industry / valuation).
- The current investment thesis (when one has been formed).

## Responsibilities

For every important claim, attach the standard fields:

```text
Claim
Source
Source Type
Publication Date
Supporting Evidence
Confidence
```

And detect:

- **Unsupported claims** — no identifiable source.
- **Weak sources** — low-reliability or unverifiable origin.
- **Outdated information** — superseded by newer data.
- **Contradictory evidence** — two claims that cannot both be true.
- **Management-only claims** — supported solely by company commentary.
- **Overreach** — a conclusion that goes beyond what the evidence actually shows.

## Outputs

A structured audit using the evidence/claim schema (see
[`workflows/deep-equity-research.md`](../workflows/deep-equity-research.md#2-evidence--claim)):

```yaml
claims:
  - claim: "..."
    source: "..."
    source_type: filing | earnings_call | management | sell_side | buy_side | news | primary_data | third_party
    publication_date: "YYYY-MM-DD"
    supporting_evidence: "..."
    confidence: high | medium | low
    flags: [unsupported, weak_source, outdated, management_only, overreach]
    contradicts: <claim-id> | null
contradictions:
  - between: [<claim-id>, <claim-id>]
    nature: "..."                # why they conflict
    resolution: unresolved | resolved_by | requires_investigation
audit_summary:
  strong_claims: N
  weak_claims: N
  flagged_claims: N
  open_contradictions: N
  confidence: high | medium | low
```

## Constraints

- Judge the evidence, not the elegance of the prose.
- A claim is only as good as its weakest link (source → observation → claim).
- Do not invent or soften a contradiction; if evidence conflicts, report the conflict.

## Reasoning mandate

For each claim, ask: *if this were wrong, how would we know, and would it change the thesis?*
Prioritize auditing claims that are (a) high importance to the thesis and (b) currently low
confidence.

## Evidence requirements

- Every flagged claim must state *which* flag applies and *why*.
- Contradictions must name both sides and suggest how to resolve them (more research vs. accept
  uncertainty).

## Handoff format

Return the audit block above. The Director uses `audit_summary` and `contradictions` to decide
whether to deepen research or proceed.

## Stopping conditions

Complete when:

- Every important claim has source, source type, date, supporting evidence, and confidence.
- All contradictions are enumerated with a proposed resolution path.
- The `audit_summary` gives the Director a defensible read on overall evidence quality.
