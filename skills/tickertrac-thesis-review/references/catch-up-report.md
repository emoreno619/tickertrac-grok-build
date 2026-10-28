# Catch-up report shape

One section per thesis, most material first. Keep the saved words; keep your reading apart.

```
## <label> (company:7:ACME, version 3)
Window: 2026-10-05T00:00Z to 2026-10-12T00:00Z (detection time). Read as of <as_of>.
Coverage: partial. <coverage.note verbatim>. Latest check <latest_check_at>; monitoring <monitoring_state>.

Saved signals: 1 support (1 material), 1 contradict (uncertain), 1 neutral (immaterial).

Support
- <title> (<source>, detected <detected_at>) — materiality: material. <summary>. Open: <app_url>
  Quote (event <event_at>, published <published_at>): "<excerpt text>" — <source_locator>

Contradict
- <title> (<source>, detected <detected_at>) — materiality: uncertain. <summary>. Open: <app_url>
  Quote: unavailable (<reason from coverage.note>).

Neutral
- <title> … (not inspected)

Saved thesis components touched: expectation "Backlog grows at least 20% a year" (support item above).

My reading (not saved): <one or two sentences of interpretation, or "none">.
Not covered: <further pages, windows beyond the cap, theses left out, or "nothing">.
```

Rules the shape enforces:

- The header names the exact subject, version, window and `as_of`.
- Coverage comes before the signals, in the words the result returned.
- Counts use the saved `relationship` and `materiality` values only.
- Each item has its `app_url`; each quote has its locator and its own dates.
- Cite a returned `source_url` only when `source_link_state` is `available`.
  Otherwise say “Source link unavailable.” Keep the saved judgment and any
  permitted quote. Label `app_url` as the TickerTrac workspace, and never invent a
  publisher/issuer destination or use a homepage in place of the exact source.
- A section with zero items reads "No retained signals in this window" plus the coverage
  note. It never reads "no news" or "nothing changed".
- "My reading" is the only place for interpretation and is always marked not saved.
- "Not covered" is never omitted; write "nothing" when the review was complete at its
  stated coverage.

For a theme, add a line listing the explicitly linked companies from `get_thesis` and keep
theme-wide findings (`theme_finding:` ids) distinct from company signals.
