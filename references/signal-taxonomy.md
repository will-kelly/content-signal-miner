# Signal taxonomy

## Source types and trust weights

Weight reflects how directly the source reflects what a buyer or user actually thinks. It is not a quality judgment; a competitor blog is a perfectly good source for gap analysis, it just can't validate a pain point.

| Type | Weight | What it's good for | What it can't do |
|---|---|---|---|
| Sales call notes / transcripts | 1.0 | Objections, buying criteria, language of people with budget | Often filtered through the rep's framing; check for rep paraphrase vs customer words |
| Support tickets | 1.0 | Pain points in the product's own vocabulary, workarounds, frequency | Skews to existing customers; silent on why prospects don't buy |
| Customer interviews / reviews (G2, Capterra, app stores) | 0.9 | Unprompted praise and complaint, comparison language | Self-selected; extremes over-represented |
| Reddit / community threads / forums | 0.8 | Raw unfiltered language, workarounds, what people recommend to each other | Anonymity invites exaggeration; one loud thread ≠ a pattern |
| LinkedIn posts (practitioners) | 0.6 | Emerging framing, what people are performing agreement with | Performative; people post what gets engagement, not what they struggle with |
| LinkedIn posts (vendors / influencers) | 0.3 | Competitive narrative, what the market is being told | Not customer voice. Treat as competitor claim |
| Competitor blogs / docs / landing pages | 0.3 | Gap analysis, their positioning, their vocabulary | Not customer voice. Never counts toward validating a pain point |
| Analyst reports / surveys | 0.5 | Scale and trend data | Aggregated; loses the actual phrasing |
| Internal opinion (exec asks, marketing hunches) | 0.2 | Fit and priority context | Not a signal. Log it so it can be tested against the corpus |

## Signal types

Tag every extracted row with exactly one.

**Pain point** — something is costing time, money, trust, or sanity. "We spend every Monday reconciling the two systems by hand."

**Objection** — a reason not to buy, adopt, or change. "Legal won't let us put customer data in anything with a model behind it."

**Workaround** — what people do instead of the intended solution. Workarounds are the highest-value signal type for content because they describe the problem and reveal the current competitor (often a spreadsheet). "We just export to CSV and do it in Sheets."

**Desired outcome** — what good looks like, in their words. "I just want to know which docs are wrong before the bot tells a customer."

**Language pattern** — a phrase, metaphor, or label that recurs. Not a complaint in itself; a way of talking. "Documentation debt." "The bot hallucinated our refund policy."

**Competitor claim** — what a competitor or vendor asserts. Logged so it can be checked against customer signals.

**Misconception** — a belief customers hold that the evidence (or the product) contradicts. These produce the best contrarian pieces when handled respectfully.

## Validation thresholds

- **Validated theme**: at least three signals, from at least two source types, at least one of which has weight ≥ 0.8
- **Unvalidated lead**: anything that recurs but misses the bar. Carried forward, labeled, never promoted to "write now"
- **Noise**: a single signal with no echo anywhere. Keep it in the ledger, don't build on it

## Trajectory labels

- **Persistent** — appears across the full time span of the corpus
- **Emerging** — appears only in the most recent third of dated material, or only in forward-looking sources (sales calls, new threads)
- **Fading** — appeared earlier, absent recently
- **Undated** — corpus has no timestamps; say so rather than guess
