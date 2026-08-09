# 05 · B2B vs B2C PM Differences

PMs move between B2B and B2C more often than they expect, and the failures
are predictable. The B2C PM arriving in B2B runs a well-designed experiment
on 300 accounts, gets nothing conclusive, and concludes the company is not
data-driven. The B2B PM arriving in B2C asks to speak to the customer who
requested a feature and is told there are eleven thousand of them.

The differences are not about industry or taste. They come from three
structural facts, and almost everything else follows:

| Structural fact | B2B | B2C |
|---|---|---|
| **Is the buyer the user?** | Usually not | Almost always |
| **How many customers?** | Hundreds to thousands | Hundreds of thousands to millions |
| **What does one customer's departure cost?** | Sometimes material on its own | Statistically invisible |

This module is about carrying the right instincts into the right context —
including the increasingly common case where a product is both.

## The comparison that matters

| Dimension | B2B | B2C | Consequence for you |
|---|---|---|---|
| **Buyer vs user** | Buyer, user, admin, economic sponsor and blocker are different people | Same person | You need a buying-committee map, not a persona |
| **Sample sizes** | Hundreds | Millions | B2B rarely powers an A/B test; B2C rarely needs interviews to detect a problem |
| **Evidence type** | Deep qualitative + win/loss + usage | Behavioural at scale | Different research budget and different confidence language |
| **Sales cycle** | Weeks to quarters | Seconds | Roadmap must serve deals in flight |
| **Churn signal** | Slow, contractual, visible in advance | Fast, silent | B2B has time to intervene; B2C must design for self-recovery |
| **Feature requests** | Named, loud, revenue-attached | Aggregate, anonymous | B2B risks becoming a bespoke shop |
| **Pricing** | Negotiated, discounted, per-seat/usage | List, tested, rarely negotiated | B2B pricing lives partly in the contract |
| **Roadmap sharing** | Customers expect one; sales promises it | Never shared | You need a public/private roadmap policy |
| **Integration depth** | Existential — must fit their stack | Optional | Integrations are roadmap, not nice-to-have |
| **Compliance** | SOC 2, GDPR, SSO, audit, procurement | Privacy and platform rules | Trust features are revenue features |
| **Switching cost** | High — data, training, contracts | Low | B2B forgives more; B2C punishes instantly |
| **Onboarding** | Implementation project | Self-serve in minutes | B2B onboarding is a product surface with a human in it |
| **Support model** | Named CSM, SLAs, QBRs | Help centre, deflection | CS is a product stakeholder in B2B |
| **Speed of feedback** | Weeks | Hours | B2C iterates faster; B2B iterates deeper |

## The buying committee is the B2B skill

In B2C you write for one person. In B2B a deal has four to seven people, and
they want incompatible things. Map them explicitly:

| Role | Cares about | Kills the deal by | ListUp example |
|---|---|---|---|
| **Economic buyer** | ROI, risk, headcount saved | "Not this year" | Agency owner |
| **Champion** | Their own visible win | Going quiet after a reorg | Ops lead who hates manual repricing |
| **End user** | Daily friction | Not adopting after purchase | Listing coordinator |
| **Technical evaluator** | Integration, data, security | Failing a review you never saw | The agency's contract developer |
| **Blocker** | Precedent, control, their own tool | A single question in the last meeting | Finance, on data residency |

The practical output: for every deal-driving feature request, know which
role is asking. "Enterprise wants SSO" is not actionable. "The technical
evaluator on three deals blocked us on SSO, worth $114k combined" is.

## Why B2B teams cannot A/B test their way out

This is the difference that most surprises people, so do the arithmetic
once and remember it.

ListUp has **286 Pro accounts**. Suppose you want to test a change to the
Pro rule builder against a baseline 30% adoption rate.

| Question | Answer |
|---|---|
| Sample needed to detect 30% → 36% (a 20% relative lift) at 95%/80% | **962 per arm** |
| Available per arm | 143 |
| Minimum lift actually detectable with 143/arm | roughly **30% → 46%** — a **55% relative** change |

So a Pro-tier experiment can only detect effects so large you would have
noticed them without an experiment. That is not a failure of rigour; it is
arithmetic. The correct B2B substitutes:

| Instead of | Use | Why it's valid |
|---|---|---|
| A/B test on small populations | **Sequential rollout with a matched comparison** — 40 accounts, watch for 6 weeks, compare against tenure/tier-matched non-recipients | Weaker causally, but honest about it |
| Statistical significance | **Effect-size-plus-mechanism** — did the accounts that adopted also tell you why, and does the story hold? | Triangulation, not p-values |
| Aggregate satisfaction | **Named-account depth** — 8 accounts studied properly | With 286 accounts, 8 is 2.8% of your market |
| "Users prefer" | **This account's admin, ops lead and owner each said** | Preserves the committee structure |

Where B2B *can* test properly: anything at the top of a self-serve funnel,
where the population is prospects rather than accounts. ListUp's 448
trials/month is a testable population; its 286 Pro accounts is not.

## Roadmap and commitments

B2C roadmaps are internal. B2B roadmaps leak, get promised, and turn into
contracts. You need a written policy before a rep needs one:

| Tier | What you share | With whom | Commitment level |
|---|---|---|---|
| **Public themes** | 3–5 directional statements, no dates | Anyone, website | None |
| **6-month outlook** | Named capabilities, quarter granularity, "subject to change" watermark | Customers under NDA | Directional |
| **Committed** | Specific capability, specific date | Named accounts only, signed by the PM | Contractual — treat as a deadline |
| **Never shared** | Anything experimental, anything in the next 4 weeks that could slip | — | — |

The rule that saves the most pain: **only the PM can move something into
"committed", and every commitment is logged with the account, the date, the
deal value and the sales owner.** If that log has more than three open
entries per quarter, you are running a consultancy.

## Metrics differ more than people expect

| Metric family | B2B version | B2C version |
|---|---|---|
| Growth | Net revenue retention, logo retention, pipeline coverage | MAU/DAU, new user growth |
| Engagement | Weekly active accounts, seats active per account, depth of feature use | DAU/MAU, sessions, time in app |
| Health | Product-qualified accounts, support tickets per account, QBR sentiment | NPS at scale, crash-free rate |
| Revenue | ACV, expansion, gross margin per account, concentration | ARPU, LTV, conversion |
| Risk | **Revenue concentration** | Platform dependency |

**Concentration** has no B2C equivalent and is the number a B2B PM should
know by heart. ListUp today is unusually safe: its largest single account is
one Pro seat at $199/mo, or **0.138%** of $143,790 MRR. Nothing any single
customer does can hurt the company.

But the strategy in Module 1 deliberately courts agencies, and an agency is
one relationship holding many accounts:

| Agency size | MRR at Pro | % of total MRR | ARR |
|---|---|---|---|
| 12 sellers | $2,388 | 1.66% | $28,656 |
| 25 sellers | $4,975 | 3.46% | $59,700 |
| 40 sellers | $7,960 | 5.54% | $95,520 |

A single 40-seller agency leaving would take **5.54% of revenue in one
email**. That is not an argument against the strategy — it is an argument
for tracking a metric you did not previously need, setting a policy
threshold (no single relationship above 8% of ARR without a board
conversation), and making sure the sellers inside an agency have their own
relationship with ListUp rather than only with the agency.

## Worked example — the same feature, two contexts

ListUp's Live Sync latency counter (Level 2) shows how differently one idea
is handled depending on the shape of the business.

| | ListUp (B2B, SMB, self-serve) | A consumer marketplace app |
|---|---|---|
| **Who asked** | 14 named accounts, 3 in open renewals worth $41k | 2,100 support contacts, no names |
| **Validation** | 8 interviews, then a 40-account rollout with matched comparison | A/B test, 90,000 users/arm, 6 days |
| **Confidence language** | "Adoption 61% vs 12% in matched accounts; three champions say it changed their workflow" | "+2.3% conversion, p=0.008" |
| **Rollout** | Beta 40 → 200 → all, with CSM briefing at each step | 5% → 50% → 100% over 4 days |
| **Failure handling** | Call the three named accounts personally | Roll back the flag |
| **Documentation** | Release note, CSM one-pager, help doc, renewal talking points | In-app tooltip |
| **Post-launch metric** | Adoption per account, renewal sentiment at QBR | Conversion, retention curve |

Same feature. Different evidence standard, different rollout, different
definition of done — and the person who tries to use the B2C column in the
B2B row will be told the change is unproven, while the person who uses the
B2B column in the B2C row will spend six weeks interviewing to learn what a
two-day test would have shown.

## The hybrid case, which is now the common case

ListUp is B2B by customer and B2C by motion: self-serve signup, no sales
call under $199/mo, and a sales-assisted agency tier above it. Products like
this need to be explicit about where the line sits, because the two motions
have incompatible defaults.

| Question | ListUp's answer |
|---|---|
| Where does self-serve stop? | Above 6 managed accounts, or any request for a contract, invoicing or security review |
| Who owns the customer above the line? | An account manager; the PM still does discovery directly |
| Can sales commit roadmap below the line? | No — self-serve accounts get the public themes only |
| Does pricing get negotiated? | Only for agency/volume; list price is never discounted for a single seller |
| Which population do we experiment on? | Trials and self-serve accounts. Agency-tier changes get sequential rollout |

Write this table for your own product. Most of the confusion in a hybrid
company is people applying one motion's rules to the other motion's
customer.

## Traps when you switch

| Coming from | Trap | Correction |
|---|---|---|
| B2C → B2B | Dismissing single-customer feedback as anecdote | One account can be 3% of revenue; weight by revenue, not count |
| B2C → B2B | Waiting for statistical significance that will never arrive | Learn the sequential-rollout and matched-comparison toolkit |
| B2C → B2B | Ignoring the buyer because the user hates it | Both must be served; the buyer signs, the user renews |
| B2B → B2C | Building for the loudest support thread | 2,000 contacts out of 4M users is 0.05% |
| B2B → B2C | Running discovery interviews for a question data can answer in a day | Interview for *why*, instrument for *whether* |
| B2B → B2C | Expecting to negotiate the roadmap with customers | There is no committee; there is a curve |
| Either | Assuming the metric names mean the same thing | Define retention, activation and churn in writing on day one |

## Exercise

1. **Classify your product** on all three structural facts: is the buyer the
   user, how many customers do you have, and what does losing the largest
   one cost as a percentage of revenue? Compute the last one.
2. **Map the buying committee** (B2B) or the decision journey (B2C) for your
   most recent significant win and most recent significant loss. Name the
   roles and who moved the outcome.
3. **Do the sample-size arithmetic** for your most important segment: how
   many units are available per arm, and what is the smallest effect you
   could actually detect? State whether A/B testing is a real option there.
4. **Write the substitute method** you will use where testing isn't
   available — sequential rollout, matched comparison, or named-account
   depth — including how many accounts and over what period.
5. **Write your roadmap-sharing policy** as a four-tier table, and list every
   open commitment your team currently has with the account, date, value and
   sales owner attached. Count them.
6. **Compute your revenue concentration**: top account, top 5, top 10, as a
   percentage of ARR. Set a threshold that would trigger action, and say who
   you would tell.
7. **If your product is hybrid**, fill in the five-row line-of-motion table.
   Circulate it to sales and CS and note every place they disagree — those
   are the real gaps.
8. **Take one feature you shipped recently** and write the two-column table
   above: how you would have validated, rolled out and documented it in the
   other model. Identify one habit worth importing.
