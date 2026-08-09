# 03 · Product-Led Growth at Scale

Product-led growth is easy to describe and hard to sustain. A product sells
itself, users onboard without a human, and the sales team — if there is one
— joins conversations the product has already started. It works beautifully
until roughly $20M ARR, at which point three things happen at once: the
cheap acquisition channels saturate, the largest customers start asking for
things a self-serve product cannot do, and someone proposes hiring a sales
team, which sets off a year-long argument about whether the company is
"still PLG".

That argument is a category error. At scale, PLG is not a business model you
either have or abandon. It is a **claim about where qualification happens**:
in the product, from usage, rather than in a conversation, from stated
intent. Everything else — sales, contracts, enterprise features — can be
layered on top without contradiction, provided the layering is driven by
what the product observed.

This module covers the PQL model, the arithmetic that decides who gets a
human, packaging at scale, and the specific ways PLG companies break as
they grow.

## Three motions, and the hybrid nobody names properly

| | Product-led | Sales-led | Hybrid (PLG + assist) |
|---|---|---|---|
| **Qualification** | Product usage | Conversation | Usage triggers the conversation |
| **First value** | Minutes, self-serve | After a demo and a pilot | Self-serve, then assisted expansion |
| **CAC** | Low, mostly fixed | High, mostly variable | Mixed — the discipline is knowing which accounts get the variable cost |
| **Deal size** | Low | High | Bimodal, which breaks averages |
| **Sales role** | None, or expansion only | Owns the whole cycle | Joins where the product signals value |
| **Fails by** | Ceiling on deal size | Cost per deal | Touching everyone, or nobody |

ListUp is the third. The hard question is not whether to have salespeople.
It is **which accounts a salesperson should ever contact** — and that is an
arithmetic question with a defensible answer.

## The product-qualified lead

A PQL is an account whose *behaviour* indicates readiness. Not a form fill,
not a job title, not a firmographic guess — an observed pattern.

A workable PQL model has three parts, and most companies build only the
first:

| Part | Question | Failure if missing |
|---|---|---|
| **Fit** | Do they look like a customer who succeeds here? | You chase accounts that will never expand |
| **Intent / readiness** | Have they done the things that precede buying? | You contact people at the wrong moment |
| **Value at stake** | How much is this account worth if it converts? | You spend the same effort on a $1,900 and a $14,000 outcome |

**ListUp's PQL score**, built by correlating each signal with 90-day
expansion among 6,150 direct accounts:

| Signal | Part | Weight | Rationale |
|---|---|---|---|
| Catalogues managed ≥ 3 | Fit | 25 | Strongest single predictor of Console attach |
| SKUs under management ≥ 500 | Fit | 15 | Proxy for the pain being expensive |
| Channels connected ≥ 4 | Fit | 10 | Core product fit |
| Opened the Decide paywall ≥ 2× in 14 days | Intent | 20 | Direct expansion intent |
| Invited a second user | Intent | 15 | Multi-user accounts expand at 2.3× |
| Published ≥ 200 changes in 30 days | Readiness | 10 | Product is load-bearing in their operation |
| Support contact about limits | Readiness | 5 | Hitting a ceiling |

Scores above 55 are "qualified". But qualification is only half the
decision.

## Who gets a human: the arithmetic

An account executive fully loaded at $190,000 can run roughly **340**
meaningful assisted sequences a year — so each touched account costs about
**$559**. That cost is the same whether the account is worth $1,920 or
$14,000, which is why a single PQL threshold across all accounts is always
wrong.

Segment the qualified population by value at stake, then compare the
conversion lift from assistance against the cost:

| Segment | Accounts | ACV uplift if converted | Assisted conv. | Self-serve conv. | Lift | EV per touch | ROI |
|---|---|---|---|---|---|---|---|
| **A — agency-shaped** (3+ catalogues, 500+ SKUs) | 430 | $14,000 | 14% | 5.0% | 9.0pt | **$1,260** | **2.25×** |
| **B — large single seller** (Publish-only, >2k SKUs) | 890 | $3,900 | 11% | 4.0% | 7.0pt | $273 | 0.49× |
| **C — standard single seller** | 2,740 | $1,920 | 9% | 3.5% | 5.5pt | $106 | 0.19× |

**Touch segment A only:**

| Line | Value |
|---|---|
| Accounts touched | 430 |
| AE capacity required | 1.26 AEs |
| Annual cost | $240,294 |
| Incremental ARR | 430 × 9.0pt × $14,000 = **$541,800** |
| **Net** | **+$301,506** (2.25× ROI) |

**Touch everyone qualified (A + B + C):**

| Line | Value |
|---|---|
| Accounts touched | 4,060 |
| Annual cost | $2,268,824 |
| Incremental ARR | $1,074,114 |
| **Net** | **−$1,194,710** |

Assisting every qualified account destroys **$1.19M a year** while
generating real, attributable, celebrated incremental revenue. This is how
PLG companies quietly become unprofitable sales-led companies: every
individual touch produces a win, and nobody computes the aggregate.

**What B and C get instead: the product.** An in-product expansion prompt at
the moment the Decide paywall is hit costs about 5 engineer-weeks
(**$19,020**) to build and roughly nothing to run:

| Prompt lift on the 3,630 B and C accounts | Incremental ARR |
|---|---|
| +1.0 point | $87,318 |
| +1.5 points | $130,977 |
| +2.0 points | $174,636 |

At a 1.5-point lift the prompt returns **$130,977 a year for a one-off
$19,020** — and unlike AE capacity, it does not need to be re-bought next
year, and it scales to 10,000 accounts at the same cost. **This is the core
economic claim of PLG at scale, stated precisely: the product is a fixed
cost and the sales team is a variable one, so people should be reserved for
the segment where the variable cost clears its own bar.**

## Packaging and the free tier at scale

| Model | Mechanism | Best when | Risk at scale |
|---|---|---|---|
| **Free trial (time)** | Full product, 14–30 days | Value is obvious quickly | Users evaluate instead of using |
| **Freemium (capacity)** | Free forever below a limit | Network or data effects; low marginal cost | Serving free users becomes a real cost line |
| **Reverse trial** | Start on the paid tier, drop to free at day 14 | Premium value needs to be experienced | Perceived as a downgrade if handled clumsily |
| **Free + paid seats** | Viewers free, editors paid | Multiplayer products | Users game the role boundary |
| **Usage-based with a free allowance** | Pay above a threshold | Value scales with volume | Revenue is hard to forecast |

Two rules that matter more at scale than at launch:

- **The free tier's job is to produce qualified accounts, not users.**
  Measure it on PQLs generated per 1,000 free accounts and on cost to serve,
  not on signup count.
- **The paywall must sit at the value boundary, not the cost boundary.**
  Gating on what is expensive for you to serve produces a free tier that
  feels arbitrary; gating on what is valuable to them produces one that
  converts.

## Metrics that matter at this stage

| Layer | Metric | ListUp | Healthy range |
|---|---|---|---|
| Acquisition | Visitors → signup | 4.1% (8,610/mo from 210,000) | 2–5% |
| Activation | Signup → activated | 52% (4,477/mo) | 30–60% |
| Monetisation | Activated → paid | 31% (1,388/mo) | 15–35% |
| Expansion | Net revenue retention, direct | 116.7% | 105–125% |
| Expansion | Multi-product attach | 47.8% of direct accounts | — |
| Efficiency | % of new ARR self-serve, no human | 71% | Above 60% for a PLG claim to be true |
| Efficiency | CAC payback, blended | 9.4 months | Under 12 |
| Assist quality | ROI on assisted touches | 2.25× (segment A only) | Above 2× |

The row that keeps you honest is **% of new ARR closed with no human
involvement**. When that number drifts below about 50%, you are a sales-led
company with a good trial experience, and you should say so — and change
your hiring, forecasting and packaging to match — rather than defending a
label.

## How PLG breaks at scale

| Failure | What it looks like | Fix |
|---|---|---|
| **Assist creep** | Sales touches every qualified account because every touch "works" | Segment by value at stake; publish the ROI per segment quarterly |
| **Two products in one** | Self-serve UX degraded by enterprise controls | Separate the surfaces: admin and governance in a console, not in the main flow |
| **Channel saturation** | Organic and paid plateau; CAC rises quarter on quarter | Invest in loops (Level 3, Module 4), not in more channels |
| **Enterprise gravity** | The roadmap becomes the top 10 accounts' requests | Cap deal-driven work as a standing allocation (Level 3, Module 6) |
| **Free tier cost drift** | Cost to serve free users grows faster than conversion | Measure cost per free account; re-fence on value |
| **Attribution wars** | Sales claims self-serve expansions | Agree the rule before compensation is designed: no touch in 30 days = self-serve |
| **Activation rot** | New features raise activation friction one point at a time | Activation is a guardrail on every launch, not a growth-team metric |

That last one deserves its own sentence. Every team adding a step to
onboarding is doing something individually reasonable, and the aggregate
effect over two years is an onboarding flow nobody would have designed.
Make activation a mandatory guardrail metric on every launch, at every
group, and review the trend annually against a holdout.

## Exercise

1. **Build your PQL model** with all three parts — fit, intent, value at
   stake. Derive weights by correlating each signal with 90-day expansion,
   and report the correlation, not your intuition.
2. **Compute your cost per assisted touch**: fully loaded AE cost divided by
   realistic annual sequence capacity. Get the capacity number from sales
   ops, not from a plan.
3. **Segment your qualified accounts by value at stake** into three tiers,
   and for each estimate assisted and self-serve conversion. If you have no
   estimate, run a hold-out for one quarter before deciding.
4. **Compute EV per touch and ROI per segment.** Draw the line where ROI
   crosses 1.0× and state how many accounts sit above it.
5. **Compute the aggregate** of touching everyone qualified. If it is
   negative, take that number to your sales leader with the per-segment
   table, not as a criticism but as a capacity plan.
6. **Design the product substitute** for the segments below the line, and
   compare its build cost against the AE cost it replaces, over three years.
7. **Audit your free tier**: PQLs generated per 1,000 free accounts, cost to
   serve, and whether the paywall sits on a value boundary or a cost
   boundary.
8. **Measure the share of new ARR closed with no human involvement.** If it
   is below 50%, write one page on what should change — the label, the
   packaging, or the motion.
9. **Check activation for rot**: plot your activation rate over 24 months and
   list every onboarding step added in that period. Propose two to remove.
