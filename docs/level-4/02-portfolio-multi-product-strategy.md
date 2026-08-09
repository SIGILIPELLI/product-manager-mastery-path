# 02 · Portfolio & Multi-Product Strategy

With one product you prioritise. With three you **allocate** — and the two
are different disciplines. Prioritisation asks which item is most valuable.
Allocation asks where the marginal engineer produces the most, which is a
question about diminishing returns, not about which idea is best.

This is the arithmetic that decides whether a multi-product company
compounds or fragments. Get it wrong in the obvious direction and you starve
a young, fast-growing line to protect a mature one that is already
throwing off cash and cannot absorb the investment. Get it wrong in the
fashionable direction and you underfund the core that pays for everything,
and discover eighteen months later that your $27M line stopped growing while
you were busy.

## The portfolio at ListUp

| Line | ARR | YoY growth | Engineers | R&D cost | ARR per engineer | R&D as % of line |
|---|---|---|---|---|---|---|
| **Publish** | $27,200,000 | 19% | 14 | $2,730,000 | $1,942,857 | 10.0% |
| **Decide** | $14,700,000 | 71% | 15 | $2,925,000 | $980,000 | 19.9% |
| **Console** | $10,500,000 | 62% | 13 | $2,535,000 | $807,692 | 24.1% |
| **Platform** | — | — | 10 | $1,950,000 | — | 3.7% of total ARR |
| **Total** | **$52,400,000** | 37.9% | **52** | **$10,140,000** | | |

The immediate temptation on seeing this table is to move engineers from
Publish (cheap to run, low growth) to Decide and Console (expensive,
fast-growing). Sometimes right. But `ARR per engineer` is a **historical**
ratio, not a marginal one, and it says nothing about what the next engineer
would produce. Publish's 19% growth on $27.2M contributes **$5,168,000** of
new ARR next year — more than Console's 62% on a smaller base contributes at
**$6,510,000**, and not far off it. Percentage growth flatters small lines.

## Three lenses, none sufficient alone

| Framework | What it asks | Use it for | Where it misleads |
|---|---|---|---|
| **Three horizons** (H1 core / H2 emerging / H3 bets) | How mature is each line? | Communicating a balanced portfolio | Encourages treating H3 as a permanent hobby with no bar |
| **70/20/10 allocation** | What proportion goes to core, adjacent, new? | A starting split when you have no data | It is a heuristic, not a finding — do not defend it as analysis |
| **Growth/share matrix** | Where do we lead, in what markets? | Deciding where to compete | Market share is unknowable in small or undefined categories |
| **Marginal ROI** | What does the next engineer produce, per line? | The actual allocation decision | Requires evidence you have to go and collect |

The first three are communication tools. The fourth is the decision tool,
and it is the one nobody does because it requires estimating something
uncomfortable.

## Marginal ROI: the number that should drive allocation

For each line, estimate what one additional engineer, sustained for a year,
would produce in incremental ARR. The estimate must come from evidence, not
enthusiasm — the best source is what happened the last time you added or
removed people from that line.

| Line | Evidence used | Marginal ARR per engineer | Confidence |
|---|---|---|---|
| **Publish** | Last 4 engineers added went to reliability and channel coverage; two new channels added $1.4M combined over 18 months | **$180,000** | High — well-measured |
| **Decide** | Attach rose 15.5% → 34% over 2 years as the squad grew from 6 to 15; each acceptance-rate point is worth ~$310k in attach | **$620,000** | Medium — confounded with the agency channel |
| **Console** | Every major agency workflow shipped has moved agency NRR; the last two added $2.1M with 4 engineers over 12 months | **$540,000** | Medium |
| **Platform** | Cuts cycle time across 42 line engineers; a 2.5% throughput gain ≈ 1 engineer-equivalent per 40 | **Indirect** | Low — must be argued on flow, not ARR |

Three disciplines make this credible rather than a wish list:

1. **Show the evidence column.** A marginal ROI with no basis is a
   preference wearing a number.
2. **Show the confidence column.** Decide's $620,000 is confounded with the
   agency channel's growth; some of that ARR would have arrived anyway.
3. **Assume diminishing returns.** These are estimates for the *next* few
   engineers, not for twenty. Re-estimate at every planning cycle, and
   expect the number to fall as a line matures.

## The multi-product effect on retention

The strongest argument for a portfolio is usually not revenue per line. It
is what happens to retention when a customer uses more than one thing.

**ListUp's 6,150 direct accounts** ($18.2M of the $52.4M; the remaining
$34.2M comes from 214 agencies at an average of $159,873 each):

| Product combination | Accounts | Share | ARPA (annual) | ARR | Net revenue retention |
|---|---|---|---|---|---|
| Publish only | 3,210 | 52.2% | $1,560 | $5,007,600 | 97% |
| Publish + Decide | 1,640 | 26.7% | $3,480 | $5,707,200 | 116% |
| Publish + Console | 520 | 8.5% | $4,020 | $2,090,400 | 121% |
| All three | 780 | 12.7% | $6,900 | $5,382,000 | 134% |
| **Total / weighted** | **6,150** | | **$2,957** | **$18,187,200** | **116.7%** |

Two things follow immediately:

- **52.2% of accounts are single-product and retain below 100%.** They are
  losing revenue every year. That population is the single largest
  identified opportunity in the company.
- **Moving 10% of Publish-only accounts (615) to Publish + Decide** is worth
  615 × ($3,480 − $1,560) = **$1,180,800**, or **2.3% of total ARR** — and
  it moves those accounts from 97% to 116% NRR, which compounds every year
  afterwards.

**The mandatory caveat**, which separates a portfolio strategy from a
correlation deck: accounts that buy a second product may simply be better
accounts. The honest test is a matched comparison — take accounts of similar
size, tenure and channel count, and compare NRR before and after attach.
Until that exists, present the number as *the size of the prize if the
relationship is causal*, and say so out loud.

## Allocation decision — ListUp's next year

**The question:** 52 engineers today, 8 more approved for next year. Where
do the 60 go?

**Option A — proportional to growth.** Fund fast-growing lines most:
Publish 12, Decide 19, Console 18, Platform 11.

**Option B — proportional to marginal ROI.** Decide and Console take
everything: Publish 12, Decide 21, Console 17, Platform 10.

**Option C — the chosen allocation:**

| Line | Now | Next year | Δ | Rationale |
|---|---|---|---|---|
| Publish | 14 | 13 | −1 | Reliability is met; channel coverage is competitive. Below 13, incident load rises — a floor, not an optimum |
| Decide | 15 | 19 | +4 | Highest marginal ROI, and it is the reason the other two lines retain |
| Console | 13 | 16 | +3 | Highest NRR combination; agency revenue is 65% of the company |
| Platform | 10 | 12 | +2 | Cross-cutting; funded on flow evidence, not ARR |
| **Total** | **52** | **60** | **+8** | |

**Why not pure marginal ROI (Option B):**

| Reason | Detail |
|---|---|
| Floors exist | Publish below 13 engineers pushes incident load onto the group that carries 52% of revenue |
| Marginal estimates decay | Decide's $620k assumes the next 4 engineers behave like the last 4. Going to +6 stretches an already-confounded estimate |
| Platform has no ARR line | Funding strictly by attributable ARR guarantees platform is never funded, then everything slows |
| Portfolios need optionality | Zero allocation to new bets means no H3 pipeline, and the current lines will mature |

**The modelled result**, at the marginal ROI estimates and each line's
existing base:

| Line | Base ARR | Base growth | Δ engineers | Marginal contribution | Modelled next-year ARR |
|---|---|---|---|---|---|
| Publish | $27,200,000 | $5,168,000 | −1 | −$180,000 | $32,188,000 |
| Decide | $14,700,000 | $10,437,000 | +4 | +$2,480,000 | $27,617,000 |
| Console | $10,500,000 | $6,510,000 | +3 | +$1,620,000 | $18,630,000 |
| **Total** | **$52,400,000** | **$22,115,000** | **+8** | **+$3,920,000** | **$78,435,000** |

That models 49.7% growth, well above the 38% plan. Two corrections before
anyone takes it to a board: growth rates decelerate as bases grow (Decide at
71% on $14.7M will not hold 71% on $25M), and marginal ROI estimates are
optimistic by construction. The planning number is **38%**, with this model
shown as the upside case and the deceleration assumption stated explicitly.
A leader who presents the unadjusted model once loses the room permanently.

## When to launch a second product

| Test | Pass condition | ListUp when Decide launched |
|---|---|---|
| **Core is healthy** | Core growth durable, NRR above 100%, no existential competitive threat | Publish at 41% growth, NRR 108% |
| **Same customer** | Sold to the same buyer through the same channel | Yes — identical buyer |
| **Real demand evidence** | Customers already paying someone else for it | 31% paying $89/mo elsewhere (Level 3, Module 1) |
| **Shared advantage** | The new product is better because of the first | 4.1M labelled price changes |
| **Funded properly** | A dedicated team, not a side project | 6 engineers, one PM, ring-fenced |
| **Kill criterion** | A number and a date agreed at launch | Under 12% attach at 18 months → stop |

Failing any single one is usually fatal. Failing "funded properly" is the
most common: second products staffed from spare capacity almost never reach
escape velocity, because they are the first thing cut whenever the core has
a bad quarter.

## When to kill a line

| Signal | Threshold | Action |
|---|---|---|
| Growth below company average for 4 quarters | And no strategic reason | Cap investment; harvest |
| Attach stalled below the kill criterion | Missed the pre-agreed date | Sunset or spin down |
| Negative contribution after fully loaded costs | 2 consecutive years | Kill |
| It exists to serve one customer | Any | Convert to services, or exit |
| Blocks the core roadmap | Persistently | Kill even if profitable |

**Killing well is a skill.** Announce internally before externally, give
customers 12 months and a migration path, redeploy the team visibly and
generously, and write down what the bet taught you. Teams watch how you
retire a failed product far more closely than how you launch a successful
one, and it sets the price of taking a risk next time.

## Portfolio governance

| Cadence | Review | Decision it can force |
|---|---|---|
| Quarterly | Line-level metrics: ARR, growth, NRR, attach, marginal ROI re-estimate | Shift up to 10% of capacity |
| Half-yearly | Portfolio review with the exec team | Shift more than 10%; open or close a line |
| Annually | Allocation for the year, with the bridge (Level 3, Module 10) | Headcount plan |
| Continuous | Kill criteria on new bets | Automatic stop when a threshold is breached |

The most valuable rule is the last: **kill criteria fire automatically.**
Something that must be argued for at the moment of failure will not be
argued for, because by then everyone in the room is invested.

## Exercise

1. **Build the portfolio table** for your company: ARR, growth, headcount,
   cost, ARR per head and R&D as a percentage of each line. If a line has no
   ARR, state what it is funded on instead.
2. **Compute dollar growth, not percentage growth**, per line. Note which
   line looks best on each measure, and which one you would have starved by
   reading only percentages.
3. **Estimate marginal ROI per line** with an evidence column and a
   confidence column. Where the evidence is weak, say what you would measure
   in the next two quarters to strengthen it.
4. **Build the attach table**: accounts by product combination, ARPA and NRR
   for each. Compute the value of moving 10% of your single-product accounts
   to two products.
5. **State the confound** in that number, and design the matched comparison
   that would settle it.
6. **Produce three allocation options** — proportional to growth, to
   marginal ROI, and your recommendation — and write the specific reasons the
   pure-ROI option is wrong, including any floors.
7. **Model the outcome** of your recommendation, then apply a deceleration
   assumption and state the planning number separately from the upside case.
8. **Score your newest bet** against the six launch tests, and write its kill
   criterion as a number and a date if it doesn't have one.
9. **Write the sunset plan** for your weakest line as if the decision were
   already made: internal announcement, customer notice period, migration
   path, and where the team goes.
