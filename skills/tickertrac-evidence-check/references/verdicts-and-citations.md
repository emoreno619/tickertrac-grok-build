# Verdict states and citation format

## Choosing the state

Read the relevant evidence on both sides before choosing a state. Conflicting directly
relevant sources mean `partial`; cite both instead of stopping at the first match. Then
work down the list.

1. **unavailable**: the only relevant records withhold their content (`excerpt_state`
   `unavailable`, empty `excerpts` with a rights or provenance reason, or a snapshot with
   `unavailable_reason`). Say what exists and why it cannot be checked here. Link `app_url`.
2. **supported** or **contradicted**: a retained passage or a saved signal with an available
   excerpt directly addresses the statement, same subject and same measure, and the retained
   text agrees or disagrees. One clear direct citation is enough; list up to three.
3. **partial**: the evidence is related but does not settle it. Typical reasons, name the one
   that applies:
   - different period or horizon (the statement is about next year; the record is last quarter);
   - related measure (backlog versus revenue; a segment versus the company);
   - one side only (a saved signal says `contradict` with materiality `uncertain`, no quote);
   - saved summary only, quote unavailable;
   - the snapshot has the figure but `freshness` is `stale` or `unknown`.
4. **insufficient**: nothing retained addresses the statement within the windows, scopes
   and queries used. State them. Absence is not evidence against the statement, and a
   bounded search (`scan_truncated`, `truncated`, page limits) is not an exhaustive one.

A numeric claim is `supported` only when the snapshot or passage gives the same measure for a
named period and the comparison holds without computing anything the record does not provide.

## Report shape

```
Statement checked: "<the user's sentence>"
Thesis: <label> (company:7:ACME, version 3). Status of the statement in the saved thesis: saved as expectation "<component>" / stated now, not in the saved thesis.

Verdict (my reading, not saved): partial — different period.

Evidence
1. Filing passage, 10-Q "Acme Robotics" section "Backlog" (event 2026-08-05, published 2026-08-05, observed 2026-08-06):
   "<exact passage text>"
   Locator: <source_locator>; artifact version <artifact_version_id>, segment <segment_id>; offsets <segment_char_start>–<segment_char_end>.
   Authority: unassessed source passage.
2. Saved signal alert:502 "<title>" (detected 2026-10-09): TickerTrac judgment contradict, materiality uncertain. Summary (TickerTrac's words): "<summary>". Quote: unavailable (<reason>). Open: <app_url>.

Searched: retrieve_thesis_evidence "robotics backlog" (filings, 2025-10-12 to 2026-10-12, 5 of 12 passages scanned, not truncated); search_evidence "backlog" (2026-09-12 to 2026-10-12).
Not covered: <windows, scopes or pages not searched; or "nothing">.
```

Rules:

- The verdict line always carries "my reading, not saved".
- Every quote is verbatim tool output with locator, ids and its own dates.
- Use `source_url` as an external citation only when `source_link_state` is
  `available`. Otherwise say “Source link unavailable” and retain the quote's
  locator, IDs and dates. A missing link does not mean a returned quote is missing.
  `app_url` opens the TickerTrac workspace; label it separately. Never infer a
  publisher or issuer link from the provider name or substitute a homepage.
- A saved summary is introduced as "TickerTrac's words"; it is never put in quotation marks as
  if it were the source.
- "Searched" lists each call with query, scope, window and truncation.
- "Not covered" is never omitted.
- Snapshot figures name `period_end`, `fiscal_period`, the filing (`form`, `filed`,
  `accession`) and `freshness`; a `missing_metrics` entry is reported as missing, not as zero.
