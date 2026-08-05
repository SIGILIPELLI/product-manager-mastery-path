# 08 · Competitive Analysis

Most competitive analysis produces a feature grid nobody reads. The reason
is that it answers the wrong question. "What do they have that we don't?"
generates a shopping list; the question you actually get asked in a roadmap
review is **"if we build this, will it still matter in a year, and if we
don't, what do we lose?"** Competitive analysis is how you answer that. It
feeds four decisions you own: what to build, what to *stop* building, how to
position, and what to charge. If your analysis doesn't change one of those
four, you wrote a report instead of doing the work.

The other trap is defining the competitive set too narrowly. Your real
competitor is usually not the other startup in your category — it's a
spreadsheet, a contractor, or the customer deciding to do nothing.

## Define the competitive set properly

List everyone who could absorb the budget and the job. Rank by how often
they actually appear in your deals, not by how much they annoy you.

| Type | Definition | ListUp examples | Why it matters |
|---|---|---|---|
| **Direct** | Same job, same category, same buyer | Channelry and other multi-channel listing tools | Sets feature expectations and the price ceiling |
| **Adjacent** | Overlapping job, different centre of gravity | Marketplace-native bulk editors; storefront app stores | Can expand into you cheaply — watch their release notes |
| **Substitute** | Different mechanism, same outcome | Enterprise PIM at ~$600/mo; a VA paid to re-type listings | Often wins on trust, not features |
| **Status quo** | Doing nothing, or the spreadsheet | Sheets plus manual copy-paste | Usually your **largest single competitor** |
| **Budget rival** | Competes for the same money, different job | Ad spend, another marketplace subscription | Explains losses that otherwise look inexplicable |

The status-quo row is the one teams skip and the one that decides most
outcomes. A seller who is "not currently evaluating anything" still has a
working process. Beating it requires a switching argument, not a feature.

## Where the evidence comes from

Rank sources by how close they sit to a real buying decision. Everything in
the top block is worth a quarter's attention; the rest is context.

| Source | Tells you | Bias to correct for |
|---|---|---|
| **Win/loss interviews** | Why deals actually turned | Buyers give the polite reason first; ask twice |
| **Churn interviews** | What you failed to keep, and to whom | Recency — the last straw isn't the cause |
| **Sales call recordings** | Objections in the buyer's own words | Reps steer toward objections they can beat |
| **Support tickets naming a rival** | Migration friction and integration gaps | Only vocal users appear |
| Competitor pricing page | Packaging, value metric, target segment | Aspirational; list price ≠ paid price |
| Competitor changelog | Direction and investment pace | Marketing-filtered; silence ≠ inactivity |
| Their job postings | Where they're investing 6–12 months out | Slow signal, but hard to fake |
| Review sites | Recurring complaints, segment fit | Incentivised reviews skew positive |
| Analyst reports | Category framing and buyer language | Pay-to-play in some categories |

**Buy the competitor's product.** One month of a paid seat teaches more than
a quarter of desk research, and it is the only way to see onboarding, error
states, and the parts that are genuinely bad.

## Compare on jobs, not features

A feature grid rewards whoever has the most checkmarks. A job grid rewards
whoever does the thing customers actually hire the product for. Score each
alternative on how well it does the job, not on whether it ships a feature
named after it.

| Job to be done | ListUp | Channelry | Marketplace-native | Spreadsheet + VA |
|---|---|---|---|---|
| Publish one listing to many channels | **Strong** | Strong | None (one channel each) | Weak (manual) |
| Catch a pricing error before it goes live | **Strong** (diff preview) | Weak (post-hoc report) | None | Weak (human check) |
| Keep stock accurate across channels | Weak | **Strong** | Partial (own channel only) | Weak |
| Set up without a developer | **Strong** (median 41 min) | Weak (CSV mapping) | Strong | Strong |
| Handle 10,000+ SKUs | Weak | Strong | Strong | None |
| Prove to a client what changed | Partial | Weak | None | **Strong** (the sheet is the log) |

Read the columns, not the cells. ListUp wins where speed and safety matter
and loses where scale and stock accuracy matter — which is a *segment*
statement, not a backlog. The correct response to "Channelry is strong on
stock accuracy" is first to ask whether our segment buys on it, and only
then to consider building.

## Turn findings into a decision

Every gap gets exactly one of four responses. Forcing the choice is the
point — an unclassified gap silently becomes a roadmap item.

| Response | Use when | Cost | ListUp example |
|---|---|---|---|
| **Differentiate** | Already ahead, and the segment buys on it | Keep investing | Pre-publish diff preview — extend it to images |
| **Neutralize** | Table stakes; losing on it blocks deals | Cheapest credible version | Stock sync, good enough to stop being a reason to lose |
| **Ignore** | Real gap, wrong segment | Zero, plus a written rationale | 10,000+ SKU support |
| **Concede** | Structurally can't win; redirect the deal | Positioning work only | Enterprise procurement, SSO, custom SLAs |

Write the rationale down for the Ignore and Concede rows. Six months later
someone will ask, and "we decided not to" is only credible with a date and a
reason attached.

## Win/loss analysis

Structured loss reasons are the highest-signal competitive input you have,
because they are recorded at the moment money didn't change hands.

**ListUp, Q3 — 380 trials that reached the evaluation stage:**

| Outcome | Deals | % of evaluations | % of losses |
|---|---|---|---|
| **Won** | 152 | **40.0%** | — |
| Lost to marketplace-native bulk tools | 91 | 23.9% | 39.9% |
| Lost to Channelry | 68 | 17.9% | 29.8% |
| Lost to spreadsheet + VA (status quo) | 49 | 12.9% | 21.5% |
| Lost to enterprise PIM | 20 | 5.3% | 8.8% |

Head-to-head win rate — the share of deals won *when that alternative was
named* — is the more actionable cut, because competitors appear in very
different volumes:

| Alternative | Deals where named | Won | Head-to-head win rate |
|---|---|---|---|
| Spreadsheet + VA | 118 | 69 | **58.5%** |
| Channelry | 143 | 75 | 52.4% |
| Enterprise PIM | 42 | 22 | 52.4% |
| Marketplace-native tools | 167 | 76 | **45.5%** |

Two findings fall out. The biggest loss bucket is marketplace-native tools,
where the head-to-head rate is also the worst — those are sellers on one or
two channels who don't yet need cross-listing, so this is a *targeting*
problem, not a product one. Second, splitting the Channelry deals by segment
is decisive:

| Segment | Channelry deals | Won | Win rate |
|---|---|---|---|
| Sellers on 1–2 channels | 62 | 21 | **33.9%** |
| Sellers on 4+ channels | 81 | 54 | **66.7%** |

Same competitor, same product, nearly double the win rate in one segment.
That one split is worth more than any feature comparison: it tells marketing
who to target, sales which deals to work, and the PM that the roadmap gap is
real only in the segment we already lose.

## The battlecard

One page, written for someone on a call with twenty seconds to read it.

| Section | Content | Length |
|---|---|---|
| Who they are | One sentence, plus their real target segment | 1 line |
| When we win | The two situations where we're clearly better | 2 bullets |
| When we lose | Honest — reps only trust a card that admits this | 2 bullets |
| Their strongest claim | Stated fairly, then answered | 1 + 1 |
| Landmine questions | Questions that expose their weakness without naming them | 3 |
| Never say | Claims that are false, unprovable, or invite a demo we lose | 2–3 |

**Landmine questions beat direct attacks.** "How do you handle a listing
that exists on three channels with different attribute names?" does more
work than "Channelry is bad at mapping" — and it doesn't age badly the week
they ship a fix.

## Keeping it alive

| Cadence | Activity | Owner |
|---|---|---|
| Continuous | Log a loss reason on every closed deal (mandatory field) | Sales |
| Monthly | Read win/loss; update head-to-head rates | PM |
| Quarterly | Refresh the job grid; re-run the four-response classification | PM |
| Quarterly | Re-buy and actually use the top competitor's product | PM |
| On trigger | Rival raises funding, ships a major release, or changes pricing | PM, within 1 week |

An analysis refreshed annually is a historical document. The mandatory
loss-reason field is the cheapest item on this list and the one that makes
everything else possible.

## Worked example — ListUp's Q3 competitive review

**Trigger:** Channelry announced funding and launched a free tier.

**What the data said:** the free tier caps users at two channels, which
targets exactly the segment where our head-to-head win rate is 33.9% and
where we were already losing to marketplace-native tools. Among 4+ channel
sellers we win 66.7%, and the cap excludes them entirely.

**Decisions taken:**

1. **Concede** the 1–2 channel segment as an acquisition target. Stop
   spending on the keywords that bring them in — they convert poorly and
   churn fast.
2. **Neutralize** stock accuracy. It was the top named reason in 29 of the
   68 Channelry losses. Build the cheapest credible sync, not the best one.
3. **Differentiate** harder on the diff preview, which appears in no
   competitor changelog and maps to the pricing-error pain already
   quantified at roughly $40 per incident.
4. **Ignore** 10,000+ SKU support. Rationale filed: the median account has
   340 SKUs and the 95th percentile is 2,100.

**Why this survived the roadmap review:** no line item came from "Channelry
has it." Each came from a loss count, a segment win rate, or a written
decision not to act — including two decisions to build nothing, which is the
part most competitive reviews are missing.

## Exercise

Run a real competitive review for your product and produce:

1. **A competitive set table** covering all five types, including status
   quo. For each, state how often it appeared in your last 20 closed deals.
2. **An evidence plan**: three sources, what each can and can't tell you,
   and the bias you'll correct for. Include one source that requires
   actually using a competitor's product.
3. **A job-based comparison grid**: 5–6 jobs, 3+ alternatives, scored on
   outcome quality rather than feature presence. Then write the
   one-sentence segment statement the columns imply.
4. **A four-response classification** of every gap you found, with a written
   rationale for each Ignore and Concede.
5. **A win/loss table** for last quarter, with both loss-share and
   head-to-head win rates, plus one segment split. If you don't record loss
   reasons today, your first deliverable is the field, not the analysis.
6. **A one-page battlecard** for your top competitor, including the "when we
   lose" and "never say" sections. Show it to a salesperson and cut anything
   they wouldn't use on a live call.
