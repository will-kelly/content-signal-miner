# Output templates

## 1. Source inventory

| ID | Source | Type | Weight | Date range | Notes |
|---|---|---|---|---|---|
| S1 | ... | Sales call notes | 1.0 | Sep–Oct 2026 | Rep paraphrase, few direct quotes |

Followed by one or two lines on coverage gaps: which source types are absent and what that limits.

## 2. Signal ledger

| ID | Quote (verbatim) | Source | Speaker | Type |
|---|---|---|---|---|
| SIG-01 | "..." | S3 | Support engineer, mid-market SaaS | Pain point |

Paraphrased rows are marked `[paraphrase]` in the quote cell. Keep it in the ledger order you extracted; sort by theme in the theme map instead.

## 3. Theme map

| Theme | Signals | Sources (n) | Source types (n) | Triangulated | Trajectory | Status |
|---|---|---|---|---|---|---|
| Review step costs more than generation | SIG-02, 07, 11, 15 | 4 | 3 | Yes | Emerging | Validated |
| Legal blocks any model touching customer data | SIG-04, 09 | 2 | 1 | No | Persistent | Unvalidated lead |

## 4. Ranked angles and verdict

| Rank | Angle | Theme | Gap type | Evidence | Whitespace | Fit | Timing | Total | Verdict |
|---|---|---|---|---|---|---|---|---|---|

Then prose:

**Write now** — three to five angles, one line each on why this one and why now.

**Hold** — angle, what's missing, which source to collect.

**Kill** — angle, one-sentence reason. Be plain. "Competitor X already owns this and SIG-14 cites their post approvingly" is a good reason. "Low score" is not.

## 5. Signal-backed brief (one per write-now angle)

### [Working title built from customer phrasing]

**Thesis** — one sentence. The claim the piece makes.

**POV statement** — one sentence the brand stands behind, written so someone could disagree with it.

**Audience** — who this is for, inferred from speaker roles in the ledger. Name the role and the situation they're in.

**Evidence block**
Three to six quoted signals with IDs. This is what makes the brief defensible. If an editor asks "says who," this answers it.

- SIG-02 — "..." (support ticket, enterprise)
- SIG-07 — "..." (Reddit, r/...)

**What competitors say** — one or two lines summarizing their framing, with source IDs.
**What they don't say** — the gap this piece fills.

**Gap type** — open ground / contrarian with receipts / standard advice failing.

**Headline variants** (four to six)
Each built from phrasing in the ledger. Mark the signal it borrows from. Example:
- "Your review step is the real cost of AI content" ← SIG-02
- "Nobody told legal the model never sees the data" ← SIG-09
Flag any variant that drifts into vendor vocabulary: `[vendor-speak — customers say "___" instead]`

**Contrarian line** — the one sentence that will make a competitor's PMM uncomfortable, and the signal IDs that let you say it with a straight face.

**Suggested structure** — four to six beats. Which signal anchors each.

**Proof to go get** — what would make this piece stronger: a named customer, a number, a screenshot, a test.

**Risks** — where the evidence is thin, where the audience might push back, what the brand should not claim.

## 6. Language bank

Grouped by theme. The literal words customers use, pulled from the ledger.

**Theme: review step costs more than generation**
- Customer words: "babysitting the output", "double work", "I read every line anyway"
- Vendor words for the same thing: "human-in-the-loop", "quality assurance layer"
- Use the customer words in headlines and subheads. Use the vendor words nowhere.

## 7. Next collection

One or two lines. The weakest validated theme and the single source type that would strengthen it most.
