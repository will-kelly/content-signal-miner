# Content signal miner

A Claude agent that turns scattered market noise into content angles with proof behind them.

Most content teams guess what to write. They chase keywords or internal opinions instead of validated signals. Most tools that try to fix this just summarize. This one decides what's worth saying, shows the evidence, and kills the weak ideas out loud.

## What it does

Feed it a pile of raw inputs — Reddit threads, sales call notes, support tickets, competitor blogs, LinkedIn posts — and it:

1. Extracts individual signals as verbatim quotes, each tagged by type and tied to a source
2. Finds patterns that recur across sources and source types (not just within one loud thread)
3. Clusters them into themes, article angles, and POV statements
4. Checks what customers say against what competitors say, and names the gaps
5. Scores every angle on evidence, whitespace, fit, and timing
6. Delivers a verdict: write now, hold, kill, with reasons

What you get back is a signal ledger, a theme map, ranked angles, a signal-backed brief for every angle that made the cut, and a language bank of the actual words customers use.

## Why it's different

**Every claim traces back.** A headline, angle, or POV with no signal IDs behind it doesn't ship. If an editor asks "says who," the brief answers.

**Source types aren't equal.** A support ticket can validate a pain point. A competitor blog can only reveal a gap. The agent weights them that way and refuses to promote a theme that only shows up in vendor material.

**It has a kill list.** The part a content lead can't get from a summarizer is a short list of ideas that looked good and don't hold up, each with one sentence on why.

**Headlines use customer words.** Variants are built from phrasing in the ledger. Anything that drifts into vendor vocabulary gets flagged with the customer alternative.

## Package contents

```
content-signal-miner/
├── SKILL.md                     # the agent — load as a Claude skill
├── system-prompt.md             # standalone version for Projects, API, or Claude Tag
├── README.md
└── references/
    ├── signal-taxonomy.md       # source trust weights, signal types, validation thresholds
    ├── scoring-rubric.md        # evidence / whitespace / fit / timing, verdict rules
    └── brief-template.md        # exact output structure, ledger through language bank
```

## Running it

**As a skill (Claude.ai or Claude Code)**
Upload the folder as a skill. It triggers on phrases like "mine these for content", "what should we write about", or "find the angles in this". Paste or attach your sources and go.

**As a Claude Project**
Paste `system-prompt.md` as the project instructions and add the three reference files to project knowledge. Drop sources into each chat.

**Via the API**
Use `system-prompt.md` as the system prompt. Send sources as user content, one message per source or a single bundled message with clear separators and dates. For the `update` mode, keep the prior run's ledger in context.

## Modes

| Mode | When | What happens |
|---|---|---|
| `mine` | Fresh corpus (default) | Full run, inventory through briefs |
| `update` | New sources added to a prior run | Extracts only the new material, re-scores, reports what changed |
| `brief` | You pick one angle from a prior run | Produces the full signal-backed brief for that angle only |

## What to feed it

Any mix of:

- Reddit or community threads (include subreddit and date)
- Sales call notes or transcripts
- Support tickets or exports
- Customer reviews (G2, Capterra, app stores)
- Competitor blog posts, docs, landing pages
- LinkedIn posts (note whether the author is a practitioner or a vendor)

More source *types* means stronger validation. A corpus of only competitor blogs produces a gap analysis but can't validate a single pain point, and the agent will say so instead of filling the hole with generic advice.

Add a line of fit context if you can: "we sell X to Y; we have standing on A and B, not C." Without it, every angle scores a neutral 3 on fit.

## Example

Input: three Reddit threads from r/techwriting, notes from six sales calls, forty support tickets, four competitor blog posts.

Output, abbreviated:

```
Theme map
| Theme                                   | Signals     | Sources | Types | Triangulated | Status     |
| Review step costs more than generation  | SIG-02,07,  | 5       | 3     | Yes          | Validated  |
|                                         | 11,15,19    |         |       |              |            |
| Legal blocks any model touching data    | SIG-04,09   | 2       | 1     | No           | Lead       |

Verdict
Write now
  1. "Your review step is the real cost of AI content" — five signals across
     tickets, calls, and Reddit; no competitor in the corpus treats review as
     a cost center. Open ground.
Hold
  - Legal / data-handling objection — two sales calls only. Get three support
    tickets or a community thread to confirm before writing.
Kill
  - "AI makes docs faster" — competitor S6 already owns this, and SIG-14
    cites their post approvingly.
```

Each write-now angle then gets a full brief: thesis, POV, audience, quoted evidence block, what competitors say and don't, headline variants with their source signals, the contrarian line, structure, proof to go get, and risks.

## Rules the agent won't break

- Never invents a quote. Paraphrase is labeled as paraphrase.
- Never counts ten comments in one thread as ten signals.
- Never fills a thin corpus with general-knowledge pain points the sources don't contain.
- Never ends with "here are twelve ideas." It ends with a decision.

## Tuning

The thresholds live in `references/`. The two most worth adjusting after your first real run:

- Validation bar in `signal-taxonomy.md` (default: three signals, two source types, one customer-facing)
- Write-now threshold in `scoring-rubric.md` (default: evidence ≥ 3 and total ≥ 14)

## Author

Will Kelly — technical content strategist focused on AI enablement. [willkelly.com](https://willkelly.com)

## License

MIT
