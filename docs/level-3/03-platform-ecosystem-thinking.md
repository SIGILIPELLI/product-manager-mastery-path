# 03 · Platform & Ecosystem Thinking

"Let's make it a platform" is the most expensive sentence in product
management. It sounds like leverage — build once, benefit many times — and
sometimes it is. More often it converts a product team that shipped features
into a team that ships abstractions nobody asked for, eighteen months before
anyone would have needed them.

The skill at Level 3 is not enthusiasm for platforms. It is **knowing the
moment a platform becomes cheaper than not having one**, and being able to
prove it with a number. Two distinct things hide under the word:

| | Internal platform | External ecosystem |
|---|---|---|
| **Customer** | Your own teams | Third-party developers, agencies, partners |
| **Success looks like** | Feature teams ship faster with less duplication | Others build things you would never have built |
| **Main cost** | Coordination and abstraction risk | Support, governance, backwards compatibility forever |
| **Fails by** | Being built too early, for imagined reuse | Having no demand side, so nobody builds |
| **Killed by** | Feature teams routing around it | One breaking change that burns partner trust |

Both are covered here, because the ecosystem usually rides on the internal
platform, and a PM who confuses them will build the API before the
abstraction underneath is stable.

## When to platformise: the rule of three, with arithmetic

The folk rule says abstract on the third occurrence. That is a decent
instinct, but you can do better than instinct.

Compare cumulative cost. A bespoke implementation costs *B* each. A platform
costs *F* up front plus *V* per implementation. Platform wins when
`B × n > F + V × n`, i.e. from `n > F / (B − V)`.

**ListUp's channel adapters.** Each new marketplace integration built
bespoke takes ~5 engineer-weeks. A shared adapter framework is estimated at
14 weeks up front, after which each channel takes ~2 weeks.

Breakeven: `14 / (5 − 2) = 4.67`, so the platform pays back on the **fifth**
adapter.

| Adapters built | Bespoke (weeks) | Platform (weeks) | Saving |
|---|---|---|---|
| 3 | 15 | 20 | −5 |
| 5 | 25 | 24 | +1 |
| 8 | 40 | 30 | +10 |
| 11 | 55 | 36 | +19 |
| 14 | 70 | 42 | +28 |

ListUp supports 11 channels and plans 3 more, so the framework is clearly
right — and would have been wrong at 3 channels. Two adjustments before you
trust this:

- **Discount the future.** Adapters 9–14 are two years out; a saving then is
  worth less than a saving now, and the roadmap may change.
- **Add abstraction risk.** If you are not confident the shared shape is
  right, inflate *V*. Getting the abstraction wrong turns a 2-week adapter
  into a 6-week fight with the framework, which flips the whole table.

Do this calculation before proposing a platform. "We keep doing this three
times" is an anecdote. "It pays back on the fifth and we have nine planned"
is a decision.

## The ecosystem question comes second

An ecosystem is a two-sided market: builders on one side, your customers on
the other. Nobody builds for an audience that isn't there, and no audience
shows up for an empty directory.

| Seeding strategy | How it works | Use when | Risk |
|---|---|---|---|
| **Build the first apps yourself** | Ship 3–5 first-party integrations on the public API | Almost always the right start | Your team competes with partners later |
| **Paid design partners** | Pay or subsidise 3 partners to build early | You have named partners already asking | They build for the cheque, not the demand |
| **Migrate existing hacks** | Formalise the integrations customers already glue together | Customers are already doing it with CSVs and Zapier | Low glamour, highest hit rate |
| **Marquee partner first** | Land one well-known integration | Credibility is your constraint | Hostage to one partner's roadmap |
| **Developer competition** | Hackathon, prizes | Late, when demand exists | Produces demos, not maintained apps |

The reliable one is the third. Before you design a directory, list every
integration your customers have already built by hand. That list is your
roadmap and your evidence of demand at the same time.

## The API is a product, and it has its own PRD

Treat an external API as a product with its own users (developers), its own
onboarding (time to first successful call), and its own irreversibility.
Every one of these decisions is hard to undo:

| Decision | Options | ListUp's choice | Why |
|---|---|---|---|
| **Auth** | API key / OAuth / both | OAuth for partner apps, keys for a seller's own scripts | Partner apps act on behalf of a seller; keys can't be scoped per app |
| **Versioning** | URL path / header / date-based | Date-based (`2026-03-01`) pinned per app | New apps get current behaviour; existing apps never break |
| **Rate limits** | Global / per-key / per-account | 600 req/min per account, burst 100/s, headers on every response | The account is the unit that gets hurt; expose remaining quota so partners can back off |
| **Pagination** | Offset / cursor | Cursor | Offsets skip records when data changes mid-page |
| **Write access** | Read-only first / full | Read-only in v1, writes in v2 behind review | A bad partner write publishes a wrong price to a real marketplace |
| **Deprecation policy** | Ad hoc / published | 12 months' notice, 6-month overlap, published on day one | The policy is the product; partners plan against it |
| **Errors** | HTTP codes only / typed codes | Stable machine-readable `error.code` plus human message | Partners parse messages if you make them |
| **Sandbox** | None / shared / per-partner | Per-partner sandbox with seeded data | Nobody should test a publish against live listings |

**The one metric that predicts adoption:** time from landing on the docs to
a successful authenticated call. Under 10 minutes and developers keep going;
over 30 and they close the tab. Measure it by watching a real developer do
it, not by estimating.

## Governance: the rules you write before you need them

| Area | Question | Why it bites later |
|---|---|---|
| Review bar | What must an app pass to list? | Ungated directories fill with abandonware and become a liability |
| Data access | What can a partner read, store, and for how long? | Determines whether you can honour deletion requests |
| Competition | May a partner build something you sell? | Answer it in public, in advance, or every partner assumes the worst |
| Support | Who does the seller contact when the partner app breaks? | Defaults to you regardless of what the contract says |
| Quality removal | When do you delist? | Removing an app that 90 sellers use needs a written path |
| Pricing | Free / listing fee / revenue share | Sets who bothers building |

The competition question deserves a written policy. ListUp's, published in
the partner terms: *we will not ship a first-party feature that duplicates a
listed partner app without 6 months' notice to that partner, and we will
never use partner-specific usage data to decide what to build.* That is
narrow, checkable, and worth more than a promise to be a good citizen.

## Worked example — ListUp opens the read API and app directory

**Context.** Following Module 1's strategy, action 2: open a read API and
partner directory so agencies and tool-builders extend ListUp. Q1 shipped
the API with 3 partners live (KR 2.3 in Module 2, scored 1.0). This is the
state 9 months later.

**What got built, and why each:**

| Component | Rationale |
|---|---|
| Read API (listings, price history, sync events) | The data partners kept asking for by CSV export |
| OAuth with per-scope consent | A seller can grant price history without granting write |
| Partner sandbox with 400 seeded listings | Removes "can I test this safely?" as an objection |
| Directory inside the ListUp app | Distribution is the thing partners actually want |
| Revenue share: 80/20 in the partner's favour | Enough to be worth building for; the platform is not the business |

**Adoption after 9 months:**

| Partner app | Installs | Price to seller | ListUp share (20%) |
|---|---|---|---|
| Accounting export | 240 | $19/mo | $912/mo |
| Analytics dashboards | 180 | $19/mo | $684/mo |
| Supplier feed sync | 95 | $19/mo | $361/mo |
| **Total** | **515** | | **$1,957/mo** |

Revenue share annualises to **$23,484** — about 1.4% of ListUp's ARR. If you
justified this programme on revenue share, you built the wrong business
case.

**The real return is retention.** 388 unique accounts have at least one
partner app installed. Their monthly logo churn is **1.3%** against **2.4%**
for comparable accounts with none.

| | Churn/mo | 12-month survival | Accounts remaining (of 388) |
|---|---|---|---|
| With ≥1 partner app | 1.3% | 85.5% | 331.6 |
| Without | 2.4% | 74.7% | 289.9 |

That is **41.7 more accounts retained** at 12 months. At $96 average monthly
revenue, retention is worth **$48,073 ARR** — roughly **2×** the revenue
share, and it compounds while the revenue share does not.

**The honest caveat, which you should state before someone else does:**
this is correlational. Accounts that install integrations are more committed
to begin with. The clean read requires a comparison of matched cohorts by
tier, channel count and tenure — and until that exists, the number is a
strong hint, not a proof. Say so in the deck. A platform business case that
overclaims once is not believed again.

**What did not work:**

| Attempt | Outcome | Lesson |
|---|---|---|
| Developer hackathon, month 3 | 14 demos, 1 maintained app | Events create prototypes; distribution creates products |
| Public write API in v1 | Pulled after a partner bulk-published 2,100 wrong prices in staging-like conditions | Ship read first; earn writes |
| Charging a $500 listing fee | 2 of 9 prospective partners walked | Do not tax the side of the market you are short of |

## Metrics for a platform or ecosystem

| Layer | Metric | ListUp at 9 months |
|---|---|---|
| **Supply** | Partners with a live, maintained app | 3 of 9 who started |
| | Time to first successful API call | 14 min median |
| **Demand** | Accounts with ≥1 app installed | 388 (21.8% of 1,780) |
| | Installs per installing account | 1.33 |
| **Quality** | Apps meeting the review bar at re-review | 3 of 3 |
| | Support tickets caused by partner apps | 12/mo, all routed to partners |
| **Value** | Churn delta, installed vs not | 1.3% vs 2.4% |
| | Revenue share | $1,957/mo |

Track supply and demand separately. A directory with 40 apps and 200
installs is failing differently from one with 3 apps and 515 installs, and
the fixes are opposite.

## Exercise

Take a product you work on and produce a platform decision, not a platform
aspiration.

1. **Find a real repetition.** Name something your team has now built at
   least twice. Estimate *B* (bespoke cost), *F* (platform fixed cost) and
   *V* (per-use cost), compute the breakeven `F / (B − V)`, and state how
   many more instances are actually on the roadmap. Conclude build or don't.
2. **Stress the estimate.** Recompute with *V* increased 50% to represent
   abstraction risk. If the decision flips, say what you would need to learn
   before committing.
3. **Inventory the hacks.** List every integration your customers have
   already built by hand — CSV exports, Zapier zaps, scripts. Rank by number
   of customers doing it. That is your ecosystem demand evidence.
4. **Write the API product decisions table** for your top candidate: auth,
   versioning, rate limits, pagination, write access, deprecation policy,
   errors, sandbox. Justify each in one line.
5. **Write the deprecation policy** in full, as you would publish it, and
   commit to a notice period.
6. **Answer the competition question in public language**: will you build
   what your partners build, and under what notice.
7. **Build the business case on retention, not revenue share.** Estimate the
   churn delta you expect, convert it to ARR, and state the confound that
   would make you wrong.
8. **Define supply, demand, quality and value metrics** with a target for
   each at 6 and 12 months, and name the number at which you would shut the
   programme down.
