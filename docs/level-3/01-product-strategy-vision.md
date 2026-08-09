# 01 · Product Strategy & Vision

Every roadmap argument you have ever lost was really a strategy argument.
When two credible people disagree about whether to build the enterprise
audit log or the mobile app, and both have customer quotes, both have
revenue attached, and both can name a competitor doing it — no
prioritisation framework settles it. RICE will happily score both. What
settles it is a prior decision about which customers you are trying to win
and how, and if nobody wrote that down, the argument gets settled by
seniority instead.

That is what strategy is for. Not inspiration — **constraint**. A strategy
is useful in exact proportion to the number of reasonable options it takes
off the table. If your strategy document would still be true if a competitor
published it, or if it does not cause you to cancel anything you are
currently doing, it is not a strategy. It is a mood.

At Level 3 you stop receiving strategy and start writing it. This module
covers the difference between vision, mission, strategy and roadmap; the
strategy kernel; how to write a diagnosis that has numbers in it; and how to
test the result before you circulate it.

## Four artefacts people confuse constantly

| Artefact | Answers | Time horizon | Changes when | Failure mode |
|---|---|---|---|---|
| **Mission** | Why we exist | Indefinite | Almost never | So broad it excludes nothing |
| **Vision** | What the world looks like if we win | 3–5 years | Rarely; a rewrite is a real event | Confused with a feature list |
| **Strategy** | Where we play and how we win | 1–3 years | When the diagnosis stops being true | A list of goals with no choices in it |
| **Roadmap** | What we're doing next and roughly when | 2–4 quarters | Every quarter | Treated as a contract instead of a bet |
| **OKRs** | How we'll know it's working | 1 quarter | Every quarter | Set before the strategy exists (Module 2) |

The chain runs downward: a roadmap item that cannot be traced to a strategic
choice is either a bug fix, a favour, or a mistake. All three exist and two
are legitimate — but you should be able to name which one it is.

## The strategy kernel

Richard Rumelt's kernel is the most useful structure in circulation because
it forces the part everyone skips. Three components, in this order:

| Component | What it is | Test it must pass |
|---|---|---|
| **Diagnosis** | What is actually going on — the crux, stated with evidence | Contains numbers; someone in the room could disagree with it |
| **Guiding policy** | Your chosen approach to the crux | Rules out at least two things you could plausibly do |
| **Coherent actions** | The small set of moves that deliver the policy, and reinforce each other | Removing any one makes the others weaker |

Most "strategy decks" open at slide 4 with the actions and never do the
diagnosis. That is why they are unarguable — and why they never survive
contact with a reorg.

### Template

Copy this and fill it in. If a cell is empty you are not done.

| Section | Prompt | Length |
|---|---|---|
| Diagnosis | What is the single hardest thing standing between us and growth? What does the data say? | 1 paragraph + a table of evidence |
| Guiding policy | Given that, what is our approach? | 1–2 sentences |
| Where to play | Which segment, which job, which channel — and which we are *not* serving | Table |
| How to win | What advantage we build that is hard to copy | 3–5 bullets |
| Coherent actions | The 3–4 moves, each with an owner and a horizon | Table |
| Explicit non-goals | What we are deliberately not doing, and what that costs us | Table |
| Proof points | What would have to be true by when for this to be working | Table |
| Falsifiers | What we would have to see to abandon this | Table |

## Worked example — ListUp's three-year strategy

**Context.** Eighteen months after the repricing in Level 2, ListUp has
1,780 paying accounts and **$1,725,480 ARR** (MRR $143,790), up 41% year on
year. Gross margin 78%. The tier mix:

| Tier | Price | Accounts | % of accounts | MRR | % of revenue | Monthly logo churn |
|---|---|---|---|---|---|---|
| Starter | $29 | 623 | 35.0% | $18,067 | 12.6% | 4.1% |
| Growth | $79 | 871 | 48.9% | $68,809 | 47.9% | 2.2% |
| Pro | $199 | 286 | 16.1% | $56,914 | 39.6% | 0.9% |
| **Total** | | **1,780** | | **$143,790** | | **2.66% blended** |

Note the gap between blended logo churn (2.66%) and revenue-weighted gross
churn (**1.92%**). The accounts leaving are disproportionately the cheap
ones. That single comparison is the seed of the whole strategy.

**Unit economics by tier**, at 78% margin, LTV capped at 36 months (an
uncapped Pro lifetime of 1 / 0.009 = 111 months is arithmetic, not a
forecast, and no board will let you spend against it):

| Tier | Implied lifetime | Uncapped LTV | LTV used (36-mo cap) | CAC | LTV/CAC |
|---|---|---|---|---|---|
| Starter | 24.4 mo | $552 | $552 | $210 | 2.6× |
| Growth | 45.5 mo | $2,801 | $2,218 | $682 | 3.3× |
| Pro | 111.1 mo | $17,247 | $5,588 | $1,400 | 4.0× |

### The diagnosis

Four pieces of evidence, gathered over one quarter:

| Evidence | Number | Source |
|---|---|---|
| Growth/Pro accounts also paying for a separate repricing or analytics tool | 31% (359 accounts) | 220-account survey + integration logs |
| Their average spend on that second tool | $89/mo | Survey, self-reported |
| Annual spend by ListUp customers on tools ListUp does not sell | **$383,412** | 359 × $89 × 12 |
| Deals lost to Channelry's free tier, last 2 quarters | 41% of Starter-segment losses | Win/loss log |

**Diagnosis:** *ListUp has won the publishing job and is losing the decision
job. Sellers use us to push a price everywhere in under five minutes, then
open a different tool to decide what that price should be. The value —
and the retention — sits in the decision. Meanwhile the bottom of our
market, where Channelry now gives away publishing for free, is 35% of our
accounts, 12.6% of our revenue, and the source of most of our churn.*

That is a diagnosis because someone could argue with it. "The 31% is
survey-inflated" is a legitimate challenge, and the strategy should survive
being asked to re-measure it.

### Guiding policy

> **Own the decision, not just the publish.** ListUp moves up the workflow
> from execution to recommendation for multi-channel sellers with four or
> more channels, and stops competing for sellers who only need free
> publishing.

This is a policy rather than a goal because it rules things out. Two obvious
options are now dead: matching Channelry's free tier, and building a mobile
app for casual sellers.

### Where to play

| | Playing | Not playing |
|---|---|---|
| **Segment** | Sellers on 4+ channels, $500k–$20M GMV, and the agencies that manage them | Solo sellers on 1–2 channels |
| **Job** | Decide *and* publish price, stock and listing content | Storefront design, fulfilment, accounting |
| **Buyer** | Owner-operator and ops lead | Enterprise procurement |
| **Channel** | Product-led trial plus agency partnerships | Outbound SDR motion |

### How to win

- **Data advantage that compounds.** Every published change and its outcome
  is a labelled training example. After 18 months of Live Sync, ListUp holds
  4.1M price changes with observed sell-through — a corpus a new entrant
  cannot buy.
- **Switching cost that customers like.** Rules, channel mappings and
  pricing history become the seller's asset, not a hostage.
- **Distribution through agencies**, who manage 8–40 sellers each and are
  paid for outcomes, not seats.

### Coherent actions

| # | Action | Horizon | Owner | Reinforces |
|---|---|---|---|---|
| 1 | Ship **rules-based repricing** in Pro, then a model-based recommendation tier | Q1–Q3 | Core PM | Actions 2 and 3 — creates the decision surface |
| 2 | Open a **read API and partner app directory** so agencies build on ListUp | Q2–Q4 | Platform PM | Action 1 — partner data enriches recommendations |
| 3 | **Agency programme**: multi-account console, volume pricing, revenue share | Q2–Q4 | GTM PM | Actions 1 and 2 — agencies are the distribution for both |
| 4 | **Stop roadmap investment in Starter**; hold it as a functional trial tier | Q1 | Core PM | Frees ~20% of engineering; concedes the segment deliberately |

Test the coherence: drop action 3 and the API has no first customers; drop
action 1 and the agency console is just a login switcher. They hold each
other up, which is the difference between a strategy and a list.

### Explicit non-goals

| Non-goal | Why | What it costs us |
|---|---|---|
| A free tier | Would subsidise the segment we are exiting | Some top-of-funnel volume; press comparisons will note it |
| Mobile app | Sellers with 4+ channels work at a desk | A recurring request from Starter users, who are not the target |
| Fulfilment or shipping | Different buyer, different data, no advantage | A plausible-sounding expansion story we will keep being asked about |
| Enterprise SSO/SOC 2 before Q4 | No deal has yet been lost on it | Blocks two named agency prospects; revisit at Q3 review |

### Proof points and falsifiers

| Horizon | Proof point | Target |
|---|---|---|
| 6 months | Pro accounts with repricing enabled | 40% of 286 = 114 |
| 12 months | Repricing attach across Growth + Pro | 30% of 1,157 = 347 accounts |
| 12 months | Incremental ARR from repricing at a $60/mo uplift | 347 × $60 × 12 = **$249,840** |
| 18 months | Revenue through agency-managed accounts | 25% of ARR |
| 24 months | Pro share of revenue | 39.6% → 55% |

| Falsifier | Threshold | Then what |
|---|---|---|
| Sellers won't delegate pricing to software | Repricing attach under 12% at 12 months with no usability blocker found | Reposition as analytics, not automation |
| Agencies want their own tool, not ours | Fewer than 8 agencies onboarded in 12 months | Cut action 3, double down on direct Pro |
| The 31% figure was survey noise | Re-measured at under 15% via integration logs | Rewrite the diagnosis before anything else |

## Testing a strategy before you circulate it

| Test | Question | Fail looks like |
|---|---|---|
| **Inversion** | Would a competent competitor plausibly choose the opposite? | "We will delight customers with quality" — nobody chooses the inverse |
| **Sacrifice** | What are we giving up? | No non-goals section |
| **Falsifiability** | What evidence would change our mind? | No numbers, so no evidence could |
| **Cancellation** | What currently-funded work stops? | The roadmap is unchanged after the strategy lands |
| **Repeatability** | Can a new engineer state it in one sentence after one read? | It takes a 30-slide deck |
| **Advantage** | Why us, and why does it get harder to copy over time? | The advantage is "we'll execute better" |

## Bad strategy, and how to recognise it in a meeting

| Tell | Example | What to ask |
|---|---|---|
| Goals dressed as strategy | "Grow ARR 40% and become the market leader" | "By doing what that we aren't doing now?" |
| Fluff | "Leverage our platform to deliver best-in-class experiences" | "Which of these words would we not say if the opposite were true?" |
| Refusing to choose | Three segments, all top priority | "If we could only serve one for 12 months, which?" |
| Template-filling | A perfect Porter's Five Forces with no decision at the end | "What did this analysis change?" |
| Strategy by acquisition of feature parity | "Close the gap with Channelry" | "Which of those gaps have we lost a deal on?" |

## Writing the vision statement

The vision describes the customer's world after you win, not your product.
ListUp's:

> **In three years, a multi-channel seller never decides a price alone.**
> Every price, every stock level and every listing change is proposed by
> ListUp from what actually sold, approved in one click, and live everywhere
> in minutes — so a seller running eight channels operates with the pricing
> discipline of a company fifty times their size.

Two properties make it usable: it is about the seller's experience, and it
is falsifiable — in three years you can check whether prices are being
proposed or typed. "Be the leading platform for e-commerce sellers" has
neither property.

## Exercise

Write a three-year strategy for a product you work on. Not a summary — the
whole kernel, with numbers.

1. **Diagnosis.** One paragraph naming the crux, plus a table of at least
   four pieces of evidence with real numbers and where each came from. Then
   write the strongest counter-argument someone could make, and say how you
   would re-measure to settle it.
2. **Guiding policy** in two sentences maximum. Then list the two plausible
   options it kills. If you cannot name two, rewrite it.
3. **Where to play / not play** across segment, job, buyer and channel.
4. **How to win** — three advantages, and for each, why it gets harder to
   copy over time rather than easier.
5. **Three or four coherent actions.** For each, write one sentence on which
   other action it reinforces. Then delete the one you are least sure about
   and check whether the rest still stand up.
6. **Explicit non-goals**, with the cost of each stated honestly. Include at
   least one that will make somebody senior unhappy.
7. **Proof points and falsifiers** — a dated table of what must be true, and
   the specific thresholds that would make you abandon the strategy.
8. **Run the six tests.** Write the result of each. Any strategy that passes
   fewer than five is not ready to circulate.
9. **A vision statement** written from the customer's point of view, in
   under 60 words, that someone could check in three years.
