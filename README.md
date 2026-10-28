# TickerTrac assistant plugin

Keep your stock research connected to why you invested.

TickerTrac helps you save why you own or are considering a company, follow evidence that could change your view, and preserve your reasoning over time.

Connect your account to bring that research into your assistant. Catch up on your Company theses and Investment themes, examine the sources behind a finding, or compare how your thesis has changed.

Try asking:

- “What challenged my investment theses this week?”
- “Does the evidence still support my assumption that demand is growing?”
- “How has my thesis changed since I first saved it?”

Reviews use evidence already saved in TickerTrac, including available filings, earnings calls and news findings. Sources, dates and coverage gaps stay visible.

A TickerTrac account is required. Start free with one monitored company. Connections begin with read access; changes require your authorization. TickerTrac provides research tools, not investment advice or trade execution.

## What it includes

- **TickerTrac saved records** connector: the hosted MCP server at
  `https://api.tickertrac.com/mcp`. You sign in through the assistant's TickerTrac
  connection (OAuth). Read access is the default; you can revoke the connection at any time
  in Assistant connections.
- **tickertrac-thesis-review**: a weekly or catch-up review of which saved Company theses
  and Investment themes had support, contradict or neutral signals in a bounded window, with
  exact sources, dates and coverage gaps.
- **tickertrac-evidence-check**: compare one assumption you state against the retained
  filings, earnings calls, disclosures, saved signals and SEC headline metrics for a saved
  thesis, and get supported, contradicted, partial, insufficient or unavailable with verbatim
  citations.

- **tickertrac-delivery**: inspect email and phone settings, preview retained updates, check
  delivery status and prepare exact preference changes for approval. It also sets up
  recurring retained reviews when the assistant host provides a persistent scheduler.

## Visual review

For a visual review, ask "Show my thesis timeline" or "Compare two saved versions of my
thesis." `get_research_view` also supports evidence catch-up, linked theme/company comparison
and existing filing/earnings comparisons. Compatible MCP Apps hosts display an interactive
view; other hosts receive the same structured records and a link to TickerTrac. Embedded
rendering depends on the host, not the model. Opening a view does not mark it reviewed.

## What it does not do

- It never performs fresh research. The server makes zero provider or model calls; every
  read returns retained records only, with explicit partial or unavailable coverage.
- It never changes your records on its own. If you ask to save a note or a source reference
  and have granted write access, the assistant prepares an exact batch for review. You can
  authorize a trusted connection to revise selected or all theses after approval in the
  conversation. That permission lasts until revoked, has no daily cap, and relies on the
  assistant to relay approval. Other changes use their existing TickerTrac review.
- TickerTrac runs monitoring and eligible email/phone delivery independently of this chat.
  Preference changes use exact approval. A recurring review inside your assistant uses that
  host's scheduler and AI allowance; availability depends on its runtime and connection.
  A one-off review creates no schedule.
- Your saved thesis is the authority. The assistant's reading is labelled as interpretation
  and is never saved as a TickerTrac judgment.

## Data

The skills send your requests to your own TickerTrac account through
`https://api.tickertrac.com/mcp` and nowhere else. The plugin stores nothing itself.
Thesis text, summaries and source excerpts returned to the assistant are private records
you chose to share with that assistant; revoking the connection stops future access but
cannot recall what the assistant already received. TickerTrac's privacy policy is at
https://tickertrac.com/privacy; terms at https://tickertrac.com/terms.

## Requirements and support

A TickerTrac account at https://tickertrac.com and an assistant that supports remote MCP
connections with OAuth sign-in. Individual assistant products differ in remote connection
support; compatibility with every host is not claimed. Setup, access controls and the
alternative local connector are documented at https://tickertrac.com/assistants. Support:
support@tickertrac.com or https://tickertrac.com/support.
