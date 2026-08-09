# 10 · Capstone — Full Product Strategy + Org Design

This is the deliverable the whole path has been building toward: a
three-year product strategy for ListUp, and the organisation that can
execute it, written as one document a board would actually accept.

The reason strategy and org design appear in the same capstone is that they
are the same decision seen from two sides. A strategy that no structure can
execute is a wish; an org chart with no strategy behind it is decoration.
Most companies produce both artefacts and never reconcile them, which is why
so many strategies survive exactly until the first planning cycle.

Below is a complete worked deliverable. Read it as a model, then produce the
same nine sections for your own product.

## What the deliverable contains

| § | Section | Answers | Length |
|---|---|---|---|
| 1 | Diagnosis | What is actually going on, including the uncomfortable part | 1 page |
| 2 | Guiding policy | Where we play and how we win | Half page |
| 3 | Coherent actions | The three or four things we will do, and what we will not | 1 page |
| 4 | Financial model | What this produces, top-down and bottom-up | 1 page |
| 5 | Org design | The structure that can execute it | 1 page |
| 6 | Hiring and bench | Who we need and when | Half page |
| 7 | Operating cadence | How decisions get made through the year | Half page |
| 8 | Risks and kill criteria | What would make this wrong, and when we stop | Half page |
| 9 | One-page strategy | The whole thing, memorable, on one page | 1 page |

---

## § 1 · Diagnosis

**Where ListUp is.** $52.4M ARR growing 37.9%. Three lines: Publish
($27.2M, 19%), Decide ($14.7M, 71%), Console ($10.5M, 62%). 6,150 direct
accounts contributing $18.2M and 214 agencies contributing $34.2M. 310
employees, 76 in R&D. Net revenue retention 112% blended, 116.7% direct.
Rule of 40 at 27.6 — below the threshold and below plan.

**Four facts that constitute the actual problem:**

| Fact | Evidence | Why it matters |
|---|---|---|
| **The revenue engine is the channel we understand least** | Agencies are 65.3% of ARR from 214 relationships; direct is 34.7% from 6,150 accounts | Concentration risk, and the roadmap is written for the smaller half |
| **Half the direct base is decaying** | 3,210 Publish-only accounts, 52.2%, at 97% NRR | The largest identified opportunity in the company, unaddressed |
| **The growth is carried by one young line** | Decide at 71% on $14.7M; Publish at 19% on $27.2M | Momentum depends on a line whose model has a known error rate |
| **Efficiency is below par while growth is above it** | Rule of 40 at 27.6; R&D at 28.3% of revenue | The next round or the next board will price this |

**The uncomfortable part, stated plainly.** ListUp is a publishing tool that
happens to sell intelligence, being paid mostly by agencies, while building
mostly for direct sellers. Every one of those clauses is defensible on its
own and together they describe a company whose investment does not match its
revenue.

**Competitive position.** Channelry is larger, better funded, and better at
channel breadth — more marketplaces, faster integrations. It has no
equivalent of Decide's 4.1M labelled price changes and no agency workflow
worth the name. It will reach parity on agency workflow in roughly 18 months
if nothing changes, and it will not reach parity on the pricing dataset
within the plan period, because that asset compounds with usage.

**The diagnosis in one sentence:** *ListUp's durable advantage is a
proprietary pricing dataset sold through an agency channel it under-serves,
while it invests as though it were a self-serve publishing tool.*

## § 2 · Guiding policy

**Where we play.** Multi-channel commerce operations for sellers doing
$2M–$200M of online GMV, reached primarily through the agencies and
aggregators that manage them.

**How we win.** A pricing and merchandising intelligence layer that improves
with every catalogue it sees, delivered inside the workflow the agency
already runs. Publishing is the entry point and the data source; it is not
the product we win on.

**What we are explicitly not doing.** Not competing on marketplace breadth
with Channelry. Not building a storefront or a commerce platform. Not
pursuing enterprise direct sales below $500k ACV. Not launching a fourth
product line inside the plan period.

The fourth exclusion is the one that will be tested most often, by the most
senior people, and it is the reason to write it down now.

## § 3 · Coherent actions

| # | Action | Why it follows from the diagnosis | Owner |
|---|---|---|---|
| **1** | **Make Decide the default, not the upsell** — attach it to every Publish account with a 60-day zero-friction trial, and move the paywall to a value boundary | 3,210 accounts at 97% NRR; attach moves them to 116% | Decide group |
| **2** | **Build the agency operating system** — multi-client workflow, approvals, white-label reporting, and an agency API | 65.3% of revenue, served by a product built for single sellers | Console group |
| **3** | **Compound the data asset deliberately** — instrument every accept/reject as a labelled example; per-slice evaluation; the review queue as a training-data engine | It is the one advantage Channelry cannot buy | Decide + Platform |
| **4** | **Hold Publish at parity, not at leadership** | Channel breadth is Channelry's game; parity is enough to keep the entry point | Publish group |

**What we stop:** the enterprise direct pipeline below $500k ACV (three
in-flight deals released to partners), the mobile app rewrite, and
one-off channel adapters requested by single agencies.

**Why this set is coherent rather than a list:** action 1 creates the usage
that produces the labels for action 3, which improves the model that makes
action 2's agency proposition defensible, which grows the channel that
distributes action 1. Publish is held flat deliberately because it feeds all
three and wins none of them. A list of four good initiatives that do not
reinforce each other is a budget, not a strategy.

## § 4 · Financial model

**Top-down plan**, with explicit deceleration:

| Year | Growth | ARR |
|---|---|---|
| Now | — | $52,400,000 |
| Year 1 | 38% | $72,312,000 |
| Year 2 | 32% | $95,451,840 |
| Year 3 | 27% | **$121,223,837** |

Three-year CAGR: **32.3%**.

**Bottom-up by line**, at each line's own decelerating rate:

| Line | Now | Year 1 | Year 2 | Year 3 | Rates |
|---|---|---|---|---|---|
| Publish | $27,200,000 | $32,368,000 | $37,546,880 | $42,803,443 | 19 / 16 / 14% |
| Decide | $14,700,000 | $25,137,000 | $38,962,350 | $56,105,784 | 71 / 55 / 44% |
| Console | $10,500,000 | $17,010,000 | $25,515,000 | $35,721,000 | 62 / 50 / 40% |
| **Total** | **$52,400,000** | **$74,515,000** | **$102,024,230** | **$134,630,227** | 42.2 / 36.9 / 32.0% |

**The bottom-up is 11.1% above the plan, and the plan is the number we
commit to.** The gap of $13,406,390 is the deceleration we believe in but
cannot yet evidence, and the discipline is to show both, name the gap, and
commit to the lower one. A leader who takes the bottom-up number to a board
gets one good quarter and then spends two years explaining a miss.

**Year-3 mix at the plan number:**

| Line | Year 3 ARR | Share | Share now |
|---|---|---|---|
| Publish | $38,541,104 | 31.8% | 51.9% |
| Decide | $50,518,807 | 41.7% | 28.1% |
| Console | $32,163,926 | 26.5% | 20.0% |

**Channel mix**, the strategy's real test:

| Channel | Now | Share | Year 3 | Share | Implied CAGR |
|---|---|---|---|---|---|
| Direct | $18,187,200 | 34.7% | $52,126,250 | 43.0% | 42.0% |
| Agency | $34,212,800 | 65.3% | $69,097,587 | 57.0% | 26.4% |

Agencies grow from 214 to roughly 320 at an average of $215,930 each, while
direct grows faster because action 1 converts the Publish-only base.
Concentration falls without the agency business shrinking, which is the only
acceptable version of de-risking a channel that funds you.

**The single largest identified move, sized:** converting 25% of the 3,210
Publish-only accounts to Publish + Decide is 802 accounts × ($3,480 −
$1,560) = **$1,540,800**, or **2.94% of current ARR**, and it moves those
accounts from 97% to 116% NRR, which compounds every year afterwards. The
caveat from Level 4, Module 2 stands: until the matched comparison is run,
this is the size of the prize if the relationship is causal.

## § 5 · Org design

**Now:** three product groups plus Platform, 76 R&D people, 52 engineers.
**Year 3:** the same four groups, with Decide split and one new capability
team.

| Group | Eng now | Eng yr 3 | Owns | Accountable for |
|---|---|---|---|---|
| **Publish** | 14 | 15 | Publishing pipeline, marketplace adapters | Reliability, parity, $38.5M line |
| **Decide — Applied** | 15 | 20 | Recommendations, thresholds, review queue, auto-apply | Attach, accepted-change value, $50.5M line |
| **Decide — Model** | (within) | 12 | Model, evaluation, data labelling engine | Per-slice accuracy, break-even precision, dataset growth |
| **Console** | 13 | 21 | Agency workflow, approvals, white-label, agency API | Agency NRR, agencies onboarded, $32.2M line |
| **Platform** | 10 | 12 | Events, API, identity, billing, cost controls | Internal SLAs, inference cost per account |
| **Total** | **52** | **80** | | |

**The one structural change that matters** is splitting Decide into Applied
and Model. Today one group owns both the model and the product surface, and
the model work is starved every time the product surface has a deadline —
which is every quarter. Splitting them makes the dataset a funded product
with its own roadmap, its own metrics, and a platform-style contract with
Applied as its named internal customer. It is action 3 expressed as
structure, which is the test of whether an action is real.

**What this structure costs, stated in advance:** two Decide groups will
disagree about thresholds, and that argument now escalates rather than being
settled in a standup. Mitigation is a written contract — Model owns
per-slice accuracy and the evaluation set, Applied owns the threshold and
the business outcome, and the break-even precision arithmetic from Level 4,
Module 7 arbitrates between them.

**Growth in R&D against revenue:**

| Year | Revenue | R&D people | Engineers | R&D cost | % of revenue | Revenue per R&D head |
|---|---|---|---|---|---|---|
| Now | $52,400,000 | 76 | 52 | $14,820,000 | 28.3% | $689,474 |
| Year 1 | $72,312,000 | 88 | 60 | $17,160,000 | 23.7% | $821,727 |
| Year 2 | $95,451,840 | 102 | 70 | $19,890,000 | 20.8% | $935,802 |
| Year 3 | $121,223,837 | 116 | 80 | $22,620,000 | 18.7% | $1,045,033 |

R&D falls from 28.3% to 18.7% of revenue **without a single reduction**,
purely because revenue compounds faster than headcount. That is the entire
Rule-of-40 recovery, and it is worth stating explicitly to a board, because
otherwise someone will propose achieving it by cutting.

## § 6 · Hiring and bench

At 6.5 engineers per PM, 80 engineers needs **12.3 PMs** against 8 today.

| Role | When | Why |
|---|---|---|
| Director, Decide | Q1 yr 1 | The split needs a leader before it needs headcount |
| PM, Decide Model | Q2 yr 1 | The dataset needs an owner, not a stakeholder |
| PM, Agency API | Q2 yr 1 | Action 2's hardest surface |
| Group PM, Console | Q4 yr 1 | Console reaches two squads' worth of scope |
| 2 × PM | Yr 2 | Ratio maintenance |
| Director, Console | Yr 2 | Second Director; VP span stays at 4 |
| 2 × PM, 1 × Group PM | Yr 3 | Ratio maintenance |

**Bench, honestly assessed:** two of the four Director-level roles in year 3
have a ready internal successor; two do not. The named development
assignments for the two internal candidates start in Q1 of year 1, because
the alternative is discovering the gap in the quarter you need it filled.

## § 7 · Operating cadence

The base cadence is the one from Level 4, Module 1. This strategy adds two
forums, because two of its actions need a decision-forcing venue that does
not currently exist.

| Cadence | Forum | Decision it can force |
|---|---|---|
| Monthly | **Model review** — per-slice accuracy, thresholds, inference cost by decile | Halt a model release on a slice regression; change the auto-apply threshold |
| Half-yearly | **Strategy check against § 8** | Stop or double an action, on the criteria rather than on the argument |

Everything else — weekly product leadership, monthly product review,
quarterly portfolio review and allocation, annual org design — stays as it
is. A strategy that requires a new meeting for every action has not been
delegated.

## § 8 · Risks and kill criteria

| Risk | Leading indicator | Kill / pivot criterion |
|---|---|---|
| Decide attach does not move the Publish-only base | Trial-to-paid on the 60-day trial | Below 8% by end of Q3 yr 1 → rebuild the offer, not the model |
| Channelry reaches agency parity early | Agency win rate in competitive deals | Below 50% for two quarters → re-price or re-scope action 2 |
| Model advantage does not compound | Labelled examples per month; per-slice accuracy trend | Flat for two quarters → the dataset is not the moat; rewrite § 1 |
| Agency concentration worsens | Top 10 agencies as % of ARR | Above 30% → direct becomes the priority regardless of efficiency |
| Inference cost inverts on heavy users | Gross margin on AI add-ons, by decile | Blended below 75% → meter it |
| The Decide split fails | Threshold disputes escalating to the VP | More than 2 per quarter → the contract is wrong, fix it before restructuring |
| Rule of 40 does not recover | Growth plus FCF margin, quarterly | Below 30 at end of yr 1 → the deceleration assumption was wrong, not the spend |

**Every criterion is a number and a date, and each fires automatically.**
Anything that has to be argued for at the moment of failure will not be
argued for.

## § 9 · The one-page strategy

> **Diagnosis.** Our durable advantage is a proprietary pricing dataset sold
> through an agency channel we under-serve, while we invest as though we
> were a self-serve publishing tool.
>
> **Where we play.** Multi-channel sellers doing $2M–$200M GMV, reached
> through the agencies that manage them.
>
> **How we win.** Pricing intelligence that improves with every catalogue it
> sees, delivered inside the agency's own workflow.
>
> **What we do.** Make Decide the default, not the upsell. Build the agency
> operating system. Compound the dataset deliberately. Hold Publish at
> parity.
>
> **What we don't do.** Channel breadth. Storefronts. Sub-$500k enterprise
> direct. A fourth product line.
>
> **What success looks like in three years.** $121M ARR at 32% CAGR, Decide
> at 41.7% of revenue, agency concentration down from 65.3% to 57% without
> shrinking, R&D at 18.7% of revenue, and Rule of 40 above 40.
>
> **What would prove us wrong.** Decide trial-to-paid below 8% by Q3, or the
> labelled dataset flat for two quarters.

Every person in the org should be able to state the second, third and fourth
paragraphs from memory. The measure of whether they can is asking five
people at random and writing down the variance in their answers.

## How this deliverable is judged

| Criterion | Fails when | Passes when |
|---|---|---|
| Diagnosis | Describes the market | Names the uncomfortable thing about *this* company |
| Guiding policy | Says what you will do | Says what you will not do, specifically |
| Coherence | Four good initiatives | Each action makes the next one work |
| Model | One optimistic number | Top-down and bottom-up, with the gap named and the lower one committed |
| Org design | Boxes | Structure derived from the actions, with its costs stated |
| Bench | Headcount only | Named successors and named gaps |
| Risk | A generic list | Numbers and dates that fire automatically |
| One-pager | A summary | Repeatable from memory by someone who did not write it |

## Stretch goals

1. **Run the matched comparison** that settles the attach causality question:
   accounts matched on size, tenure and channel count, NRR before and after
   attach. Rewrite § 4's largest move with the corrected number, and state
   how much of the $1,540,800 survives.
2. **Build the sensitivity model.** Recompute the three-year plan at Decide
   growing 55/40/30 instead of 71/55/44, and write the org design that
   version implies. If the structure does not change, one of the two
   documents is not real.
3. **Write the losing version.** Produce the strategy Channelry would write
   to beat this one, in the same nine sections, then list the three things it
   exploits and what you would change in response.
4. **Cost the org design properly**, including the productivity dip of the
   Decide split — four to eight weeks — and the recruiting cost of 12 hires
   at senior product level. Compare the total against the incremental ARR the
   structure is supposed to unlock.
5. **Write the year-1 falsification review in advance**: the exact table you
   will fill in twelve months from now, with the kill criteria as rows and
   blank cells for the actuals. Put the date in the calendar before you
   present the strategy.
6. **Reconcile the strategy with individual objectives.** Trace one action
   from § 3 down to a named PM's quarterly objective, and back up again. Any
   action that does not survive the round trip is not funded, whatever the
   document says.
7. **Present it in ten minutes to a hostile audience** using Level 4,
   Module 5's structure — bottom line, evidence, risk, ask — and have someone
   play the board member whose only question is why growth decelerates from
   38% to 27% while headcount rises 53%.
