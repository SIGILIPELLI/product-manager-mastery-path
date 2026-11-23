---
title: "Product Manager Cheat Sheet: Quick Reference, Beginner to Advanced"
description: "A free Product Manager cheat sheet: 39 quick-reference tables from every level of the Product Manager Mastery Path, each linked to its full lesson."
---

# Product Manager Cheat Sheet

Quick-reference tables from **39 lessons** of the free Product Manager Mastery Path, in course order from beginner to advanced. Each section links to the full lesson with explanations and runnable examples.

## Level 1 · Entry

### [01 · What Is Product Management?](level-1/01-what-is-product-management.md)

*What a PM is actually responsible for*

| Responsibility | What it looks like day to day |
|---|---|
| Understanding the customer | Interviews, support ticket review, usage data analysis |
| Defining the problem | Turning vague pain ("users churn a lot") into a specific, testable problem statement |
| Setting priorities | Deciding what the team works on next, and — just as importantly — what it doesn't |
| Writing requirements | PRDs, user stories, acceptance criteria that engineering and design can build from |
| Aligning stakeholders | Getting sales, support, leadership, and legal rowing in the same direction |
| Measuring outcomes | Defining success metrics before launch, checking them after |
| Making the tradeoff calls | Speed vs. quality, scope vs. deadline, one segment's needs vs. another's |

### [02 · Understanding Customers &amp; Users](level-1/02-understanding-customers-users.md)

*Customer interviews*

| Bad question (hypothetical/leading) | Better question (behavioral) |
|---|---|
| "Would you use a dashboard that shows X?" | "Walk me through the last time you needed to check X — what did you do?" |
| "Do you think notifications are annoying?" | "Tell me about the last notification you got from this product. What did you do with it?" |
| "Would a cheaper plan make you buy more?" | "What made you choose your current plan over the others?" |
| "Do you want more customization options?" | "Tell me about a time the default setup didn't work for you. What did you do?" |

### [03 · Problem Discovery](level-1/03-problem-discovery.md)

*Signals vs. problems*

| Signal (raw, as received) | Possible underlying problem (needs validation) |
|---|---|
| "Add a dark mode" (one support ticket) | Might be a genuine accessibility/eye-strain issue, or one vocal user's preference |
| Churn spiked 15% this month | Could be onboarding, pricing, a competitor launch, or a bug — undetermined until investigated |
| "Sales says three deals were lost because we lack SSO" | Likely a real, quantifiable problem — but confirm it's not one deal's excuse |
| Weekly active users flat for two quarters | Vague; could be dozens of different underlying causes |

### [04 · Prioritization Basics](level-1/04-prioritization-basics.md)

*RICE — a scoring model for comparing initiatives*

| Factor | Question it answers | Typical scale |
|---|---|---|
| **Reach** | How many users/accounts does this affect in a given period? | A real number, e.g. "400 users/quarter" |
| **Impact** | How much does it move the needle for each user affected? | 3 = massive, 2 = high, 1 = medium, 0.5 = low, 0.25 = minimal |
| **Confidence** | How sure are we about the Reach/Impact estimates? | 100% = high confidence, 80% = medium, 50% = low |
| **Effort** | How much team-time will this take (person-months)? | A real number, e.g. "1.5" |

### [05 · Writing Requirements](level-1/05-writing-requirements.md)

*User stories*

| Weak story | Strong story |
|---|---|
| "Add a filter dropdown to the reports page." | "As a team lead reviewing weekly reports, I want to filter results by team member, so that I can check one person's numbers without scanning the whole list." |
| "Build an export button." | "As an ops manager, I want to export the current filtered view to CSV, so that I can share results with people who don't have product access." |

### [06 · Working with Design &amp; Engineering](level-1/06-working-with-design-engineering.md)

*When to loop in design and engineering*

| Stage | Design involvement | Engineering involvement |
|---|---|---|
| Problem discovery (Module 3) | Informal — can offer perspective on past user pain points | Informal — can flag "we already tried this" or technical context |
| Drafting the problem statement/goals | Light review for sanity-check | Light review for sanity-check |
| Drafting user stories | Active — starts sketching flows in parallel | Active — starts flagging feasibility/complexity concerns |
| Acceptance criteria & scope | Co-written with design and engineering, not handed to them | Co-written with design and engineering, not handed to them |
| Build | Design reviews implementation against intent | Engineering owns technical decisions |

### [07 · Metrics &amp; KPIs Basics](level-1/07-metrics-kpis-basics.md)

*North Star metric*

| Product | Weak North Star (lagging/vague) | Better North Star (leading, specific) |
|---|---|---|
| Music streaming app | Total revenue | Weekly hours of music listened per active user |
| Project-management SaaS | Total signups | Number of teams with 3+ active weekly users |
| Ride-sharing app | Total rides | Weekly active riders who complete a ride |
| Photo-editing app | Downloads | Monthly active users who export/share an edited photo |

### [08 · Roadmapping Basics](level-1/08-roadmapping-basics.md)

*Theme-based vs. feature-list roadmaps*

| Approach | What it looks like | Risk |
|---|---|---|
| **Feature-list roadmap** | "Q3: Dark mode. Q4: SSO. Q1 next year: Mobile app." | Reads as a fixed commitment; painful to change; encourages building the listed thing even after new evidence suggests otherwise |
| **Theme-based roadmap** | "Q3: Reduce onboarding friction. Q4: Enterprise readiness." | Communicates *intent and priority* without over-committing to a specific solution; leaves room for discovery to shape the actual feature |

### [09 · Stakeholder Communication Basics](level-1/09-stakeholder-communication-basics.md)

*Mapping your stakeholders*

| Stakeholder | What they care about | What they need to hear |
|---|---|---|
| Engineering lead | Scope clarity, technical risk, timeline realism | Confirmed requirements, any scope changes, blockers |
| Design lead | Whether the problem/user need is still accurately represented | Any changes to the problem statement or user stories |
| Sales | Whether/when a feature can be promised to a prospect | Honest confidence level and rough timing (see Module 8) |
| Customer support | What's changing that will generate tickets | What's shipping, when, and any known rough edges |
| Executive/leadership | Business impact, how this ties to company goals | Progress against the success metric and the "why" |

## Level 2 · Intermediate

### [01 · Advanced Discovery](level-2/01-advanced-discovery.md)

*Jobs-to-be-Done: what the customer hired the product to do*

| Solution-framed (what you'll hear) | Job-framed (what to write down) |
|---|---|
| "Add a bulk CSV upload" | When I add a new season's stock all at once, I want every item listed without re-typing it per marketplace, so I can start selling the day it arrives |
| "We need a Slack integration" | When something breaks in a live campaign, I want to find out where I already am, so I can react before the client notices |
| "Give us more dashboard charts" | When my boss asks how the quarter is going, I want a defensible number in under a minute, so I can answer without looking unprepared |

### [02 · Prioritization Frameworks Deep Dive](level-2/02-prioritization-frameworks-deep-dive.md)

*Weighted scoring*

| Criterion | Weight | 1 means | 5 means |
|---|---|---|---|
| Outcome impact | 0.35 | No plausible link to the quarter's outcome | Directly moves the outcome metric |
| Reach | 0.20 | Under 10% of active accounts | Nearly every active account |
| Confidence | 0.15 | One anecdote | Interviews + analytics + support agree |
| Effort (inverted) | 0.20 | Multi-quarter | Under a week |
| Strategic fit | 0.10 | Off-strategy; we'd have to explain it | Extends our stated wedge |

### [03 · A/B Testing &amp; Experimentation Basics](level-2/03-ab-testing-experimentation-basics.md)

*Writing a testable hypothesis*

| Weak | Rewritten |
|---|---|
| "New pricing page will convert better" | Because 61% of pricing-page sessions end without scrolling past the fold (analytics, Q2), we believe adding a plan-comparison table above the fold for first-time visitors will raise visitor→trial from 4.0% to 5.0%. We'll know when the primary metric clears +25% relative and trial→paid does not fall below 20%. |
| "Users will like the new onboarding" | Because 41% of new accounts abandon at the API-key step (funnel, n=1,180), we believe replacing the key field with guided screenshots will raise step completion from 59% to 70%, without raising support tickets per new account. |

### [04 · Product Analytics](level-2/04-product-analytics.md)

*The event model comes first*

| Element | Rule | Good | Bad |
|---|---|---|---|
| Event name | `object_action`, past tense, snake_case | `listing_published` | `Publish!`, `user did publish` |
| Granularity | One event per meaningful user action, not per click | `marketplace_connected` | `button_clicked` (with 40 meanings) |
| Properties | Everything you'd want to segment by, on the event itself | `marketplace: "B"`, `listing_count: 47`, `plan: "growth"` | Properties looked up later from a different table |
| Identity | Same user ID pre- and post-signup; alias anonymous IDs | `user_id` stitched at signup | Anonymous sessions orphaned |
| Ownership | A tracking plan in version control, reviewed like an API | One spreadsheet/repo, one owner | Ad-hoc events added per feature |

### [05 · Go-to-Market Basics](level-2/05-go-to-market-basics.md)

*Positioning before messaging*

| Component | Question | ListUp example |
|---|---|---|
| **Competitive alternative** | What would they do if we didn't exist? | Re-typing listings by hand, or a $600/mo enterprise PIM |
| **Unique attributes** | What do we have that alternatives don't? | One edit publishes to every connected channel, with a pre-publish diff |
| **Value** | What does that attribute *do* for them? | A season's stock is live everywhere the day it lands, with no pricing mistakes |
| **Target segment** | Who cares most about that value? | Sellers on 2+ channels with 100–2,000 SKUs and no ops staff |
| **Market category** | What frame makes the value obvious? | Multi-channel listing management (not "e-commerce tools") |

### [06 · Working with Data Teams](level-2/06-working-with-data-teams.md)

*Who does what*

| Role | Optimises for | Bring them | Don't bring them |
|---|---|---|---|
| **Data/analytics engineer** | Reliable pipelines and models of the data warehouse | New event sources, broken tables, a metric that needs to exist for everyone | One-off questions |
| **Product analyst** | Answering questions that change decisions | Diagnostics, funnel/cohort deep dives, experiment readouts | Dashboard maintenance you could self-serve |
| **Data scientist** | Prediction, causal inference, modelling | Forecasting, propensity/ranking models, quasi-experimental analysis | Descriptive counts |
| **Analytics/BI tooling owner** | Self-serve access and definition governance | Instrumentation reviews, metric definitions, access | Analysis |

### [07 · Agile/Scrum for PMs](level-2/07-agile-scrum-for-pms.md)

*Roles, honestly*

| Role | Owns | In practice |
|---|---|---|
| **Product Manager** | Problem, outcome, strategy, discovery, launch | In smaller orgs, also the PO |
| **Product Owner** | Backlog order, story acceptance, in-sprint clarification | A Scrum role, not a career; often the same person as the PM |
| **Scrum Master / Delivery lead** | Process health, removing impediments | Not your boss and not your assistant |
| **Engineering** | Technical design, estimates, *how* | Estimates are theirs. Full stop |
| **Design** | Interaction and visual solution | Should be in refinement, not handed a spec |

### [08 · Competitive Analysis](level-2/08-competitive-analysis.md)

*Define the competitive set properly*

| Type | Definition | ListUp examples | Why it matters |
|---|---|---|---|
| **Direct** | Same job, same category, same buyer | Channelry and other multi-channel listing tools | Sets feature expectations and the price ceiling |
| **Adjacent** | Overlapping job, different centre of gravity | Marketplace-native bulk editors; storefront app stores | Can expand into you cheaply — watch their release notes |
| **Substitute** | Different mechanism, same outcome | Enterprise PIM at ~$600/mo; a VA paid to re-type listings | Often wins on trust, not features |
| **Status quo** | Doing nothing, or the spreadsheet | Sheets plus manual copy-paste | Usually your **largest single competitor** |
| **Budget rival** | Competes for the same money, different job | Ad spend, another marketplace subscription | Explains losses that otherwise look inexplicable |

### [09 · Pricing Basics](level-2/09-pricing-basics.md)

*Start with the value metric, not the number*

| Test | Question | Fails if |
|---|---|---|
| **Aligned** | Does the customer's bill grow as they get more value? | Charging by API call when value comes from accuracy, not volume |
| **Predictable** | Can the customer forecast next month's bill? | Pure usage metrics that spike without warning |
| **Countable** | Can both sides agree on the number without arguing? | "Monthly active contributors" with a fuzzy definition |
| **Expandable** | Does it grow naturally as the account succeeds? | Flat per-company fee — a customer 10× larger pays the same |

### [10 · Project — GTM Plan for a Feature Launch](level-2/10-project-gtm-plan.md)

*The launch brief*

| Field | Value |
|---|---|
| **Feature** | ListUp **Live Sync** — price and inventory changes propagate to every connected marketplace in under 5 minutes, replacing a 4–6 hour batch |
| **Launch tier** | T1 — flagship capability, changes the product's core promise, gated to paid tiers |
| **Launch date** | Tuesday, week 0 (Tue–Thu ships best; avoid Mondays and Fridays) |
| **Lead time** | 6 weeks |
| **PM (DRI)** | You |
| **Eligible audience** | 769 accounts on Growth and Pro (of 1,240 paying) |
| **Budget** | $10,700 |
| **One-sentence pitch** | Change a price once and it's live everywhere before your next customer sees the old one |

## Level 3 · Advanced

### [01 · Product Strategy &amp; Vision](level-3/01-product-strategy-vision.md)

*Four artefacts people confuse constantly*

| Artefact | Answers | Time horizon | Changes when | Failure mode |
|---|---|---|---|---|
| **Mission** | Why we exist | Indefinite | Almost never | So broad it excludes nothing |
| **Vision** | What the world looks like if we win | 3–5 years | Rarely; a rewrite is a real event | Confused with a feature list |
| **Strategy** | Where we play and how we win | 1–3 years | When the diagnosis stops being true | A list of goals with no choices in it |
| **Roadmap** | What we're doing next and roughly when | 2–4 quarters | Every quarter | Treated as a contract instead of a bet |
| **OKRs** | How we'll know it's working | 1 quarter | Every quarter | Set before the strategy exists (Module 2) |

### [02 · OKRs for Product Teams](level-3/02-okrs-for-product-teams.md)

*Anatomy*

| Element | Question | Count | Rule |
|---|---|---|---|
| **Objective** | What are we trying to achieve, in plain language? | 2–3 per team per quarter | Qualitative, memorable, no numbers |
| **Key result** | How will we know we achieved it? | 2–4 per objective | Numeric, with a baseline, a target and a date |
| **Initiative** | What we'll do to move the KR | Any number | Never a KR; these are your bets, not your commitments |
| **Health metric** | What must not get worse while we chase this | 1–2 per objective | Guardrail; breaching it cancels the win |

### [03 · Platform &amp; Ecosystem Thinking](level-3/03-platform-ecosystem-thinking.md)

| | Internal platform | External ecosystem |
|---|---|---|
| **Customer** | Your own teams | Third-party developers, agencies, partners |
| **Success looks like** | Feature teams ship faster with less duplication | Others build things you would never have built |
| **Main cost** | Coordination and abstraction risk | Support, governance, backwards compatibility forever |
| **Fails by** | Being built too early, for imagined reuse | Having no demand side, so nobody builds |
| **Killed by** | Feature teams routing around it | One breaking change that burns partner trust |

### [04 · Growth Product Management](level-3/04-growth-product-management.md)

*Core PM vs growth PM*

| | Core product | Growth product |
|---|---|---|
| **Question** | Does this solve the problem? | Does the system convert better? |
| **Unit of work** | Feature | Experiment |
| **Typical horizon** | 1–2 quarters | 1–3 weeks |
| **Success** | Retention, satisfaction, job done | Conversion rate, LTV, payback |
| **Failure is** | Expensive and slow to detect | Cheap and expected — 60–80% of tests lose or are flat |
| **Main risk** | Building the wrong thing | Local maxima; short-term wins that cost retention |

### [05 · B2B vs B2C PM Differences](level-3/05-b2b-vs-b2c-pm-differences.md)

| Structural fact | B2B | B2C |
|---|---|---|
| **Is the buyer the user?** | Usually not | Almost always |
| **How many customers?** | Hundreds to thousands | Hundreds of thousands to millions |
| **What does one customer's departure cost?** | Sometimes material on its own | Statistically invisible |

### [06 · Working with Sales &amp; Customer Success](level-3/06-working-with-sales-customer-success.md)

*The tension, stated honestly*

| | Sales | Customer Success | Product |
|---|---|---|---|
| **Paid on** | Bookings this quarter | Renewal and expansion | Outcomes over years |
| **Time horizon** | 30–90 days | 90–365 days | 1–3 years |
| **Sees** | Deals that nearly closed | Customers at risk now | The whole system |
| **Systematically over-weights** | The last deal lost | The loudest at-risk account | Its own strategy |
| **Systematically under-weights** | Whether the feature was the real blocker | Accounts that quietly renew | Revenue in flight |

### [07 · Product Ops Basics](level-3/07-product-ops-basics.md)

*The three pillars*

| Pillar | Owns | Symptom when missing |
|---|---|---|
| **Data & insights** | Metric definitions, event taxonomy, self-serve dashboards, research repository, feedback taxonomy | Three decks with three different numbers for "active accounts" |
| **Process & cadence** | Planning rhythm, launch tiering, intake, release notes, roadmap format, review templates | Every quarter's planning is redesigned from scratch |
| **Tooling & knowledge** | The product stack, permissions, templates, onboarding for new PMs | New PM takes 10 weeks to be useful; nobody can find last year's decision |

### [08 · Advanced Experimentation](level-3/08-advanced-experimentation.md)

| Situation | What breaks | Covered here |
|---|---|---|
| You check results daily | The false-positive rate, badly | Peeking |
| You read 12 metrics per test | The false-positive rate, again | Multiple comparisons |
| The population is too small | Nothing is ever significant | Variance reduction, alternative designs |
| Treatment leaks between arms | Randomisation | Switchbacks, cluster assignment |
| A year of wins produces no visible movement | Your belief in the whole programme | Holdouts and meta-analysis |

### [09 · Managing Technical Debt &amp; Platform Investments](level-3/09-managing-technical-debt-platform-investments.md)

*Not all debt is the same*

| | **Prudent** | **Reckless** |
|---|---|---|
| **Deliberate** | "We ship the simple version now, and we know the cost" — legitimate, needs a written trigger for repayment | "We don't have time for design" — a management failure, not an engineering one |
| **Inadvertent** | "Now we know how it should have been built" — unavoidable and healthy | "What's layering?" — a capability gap; hiring and mentoring problem |

### [10 · Project — Product Strategy Doc + OKRs](level-3/10-project-strategy-okrs.md)

*Year in review — did last year's strategy work?*

| Proof point | Target | Actual | Verdict |
|---|---|---|---|
| Pro accounts with repricing enabled, 6 months | 114 | 98 | Miss |
| Repricing attach across Growth + Pro, 12 months | 30% (347 accounts) | **15.5%** (271 accounts) | **Miss, badly** |
| Incremental ARR from repricing at $60/mo uplift | $249,840 | $195,120 | Miss |
| Revenue through agency-managed accounts, 18-month target | 25% | **21.8% at 12 months** | Ahead of pace |
| Pro share of revenue, 24-month target | 55% | **50.1% at 12 months** | Well ahead |

## Level 4 · Master

### [01 · Leading Product Orgs](level-4/01-leading-product-orgs.md)

*What changes at each altitude*

| | Senior PM | Group PM / Director | VP Product |
|---|---|---|---|
| **Output** | Product decisions | Your team's decisions | The org's decision quality |
| **Time horizon** | 1–2 quarters | 2–4 quarters | 1–3 years |
| **Main input** | Customers, data | Your PMs, peers in eng/design | Board, market, exec peers |
| **Main risk** | Wrong feature | Wrong team boundaries | Wrong strategy or wrong people |
| **How you scale** | Prioritise better | Delegate with context | Hire, design the org, set operating rhythm |
| **Failure mode** | Overcommitting | Becoming a super-PM | Becoming a scheduler |
| **What you must stop** | Doing design and QA yourself | Writing the PRDs | Making the calls your directors should make |

### [02 · Portfolio &amp; Multi-Product Strategy](level-4/02-portfolio-multi-product-strategy.md)

*The portfolio at ListUp*

| Line | ARR | YoY growth | Engineers | R&D cost | ARR per engineer | R&D as % of line |
|---|---|---|---|---|---|---|
| **Publish** | $27,200,000 | 19% | 14 | $2,730,000 | $1,942,857 | 10.0% |
| **Decide** | $14,700,000 | 71% | 15 | $2,925,000 | $980,000 | 19.9% |
| **Console** | $10,500,000 | 62% | 13 | $2,535,000 | $807,692 | 24.1% |
| **Platform** | — | — | 10 | $1,950,000 | — | 3.7% of total ARR |
| **Total** | **$52,400,000** | 37.9% | **52** | **$10,140,000** | | |

### [03 · Product-Led Growth at Scale](level-4/03-product-led-growth-at-scale.md)

*Three motions, and the hybrid nobody names properly*

| | Product-led | Sales-led | Hybrid (PLG + assist) |
|---|---|---|---|
| **Qualification** | Product usage | Conversation | Usage triggers the conversation |
| **First value** | Minutes, self-serve | After a demo and a pilot | Self-serve, then assisted expansion |
| **CAC** | Low, mostly fixed | High, mostly variable | Mixed — the discipline is knowing which accounts get the variable cost |
| **Deal size** | Low | High | Bimodal, which breaks averages |
| **Sales role** | None, or expansion only | Owns the whole cycle | Joins where the product signals value |
| **Fails by** | Ceiling on deal size | Cost per deal | Touching everyone, or nobody |

### [04 · M&amp;A and Product Integration](level-4/04-ma-and-product-integration.md)

*First: is buying even the right instrument?*

| | Build | Buy | Partner |
|---|---|---|---|
| **Cost profile** | Predictable, mostly people | Large, up front, plus integration | Low, ongoing revenue share |
| **Time to value** | 12–24 months | 3–9 months, if integration goes well | 1–3 months |
| **Control** | Total | High, degrades if the team leaves | Low |
| **Learning retained** | All of it | Only if the team stays | Little |
| **Main risk** | Too slow; opportunity lost | Overpay; team leaves; integration stalls | Partner's roadmap and survival |
| **Use when** | Core to the strategy, and you have time | The gap is capability plus market, and time matters | Adjacent, not core |

### [05 · Executive Communication &amp; Board Reporting](level-4/05-executive-communication-board-reporting.md)

*The two audiences are not the same*

| | Exec team | Board |
|---|---|---|
| **Frequency** | Weekly to monthly | Quarterly |
| **Context they hold** | Most of it | Almost none — reconstruct it every time |
| **What they want** | Decisions, trade-offs, unblocking | Confidence in the plan and in the team |
| **Time budget** | 15–30 min | 5–10 min of the agenda is yours |
| **Their real question** | "What do you need from me?" | "Is this team going to hit the plan, and do they know why or why not?" |
| **Detail tolerance** | High, if it is decision-relevant | Low — detail belongs in the pre-read appendix |
| **Bad news reaction** | Wants the fix | Wants evidence you saw it early and have a plan |
| **How you lose them** | Status without an ask | Metrics without a narrative, or narrative without metrics |

### [06 · Building Product Culture](level-4/06-building-product-culture.md)

*Norms, and the artefact that encodes each*

| Norm | The artefact that encodes it | What happens without it |
|---|---|---|
| Decisions are written down | A one-page decision record with owner, options, and rationale | The same argument is re-litigated every quarter |
| Claims come with evidence | The "how do you know?" column in every review template | Confident people win over correct people |
| Experiments are pre-registered | A registry with hypothesis and success criteria filed before launch | Post-hoc rationalisation of every result |
| Negative results are published | A standing agenda item in the monthly product review | Teams learn to hide failure, then to avoid risk |
| Customers are met directly | A quota — every PM does 3 customer conversations a month, logged | Product opinions drift into internal folklore |
| Strategy is repeatable by anyone | The one-page strategy, restated in every all-hands | Eight teams optimise eight different things |
| Disagreement is aired, then committed to | An explicit disagree-and-commit protocol with a named decider | Passive resistance in the execution phase |
| Bad news travels up fast | Leaders visibly thank the person who brought it | You find out from the churn report |
| Launches have pre-set success criteria | Criteria fixed in the launch doc before code is written | Everything is a success in retrospect |
| Postmortems are blameless | A template with no "who" field and a published output | The cause is recorded as "human error" and recurs |

### [07 · AI/ML Product Management](level-4/07-ai-ml-product-management.md)

*What is genuinely different*

| Dimension | Deterministic product | AI/ML product |
|---|---|---|
| **Correctness** | Binary — works or is a bug | A distribution; there is an error *rate* |
| **Spec** | Describes behaviour | Describes acceptable error and its cost |
| **QA** | Test cases pass | An evaluation set with a score and a regression bar |
| **Failure** | Visible, reproducible | Often silent, plausible, and confidently wrong |
| **Improvement** | Write code | Data, evaluation, then sometimes a model |
| **Marginal cost** | ≈ 0 | Real, per inference, and scales with success |
| **Latency** | Predictable | Variable, sometimes seconds |
| **Regression risk** | Caught by tests | A model update can silently degrade a subgroup |
| **Trust** | Assumed | Earned, and lost permanently by one bad experience |
| **Roadmap unit** | Feature | Capability plus threshold plus fallback |

### [08 · Crisis Management for Products](level-4/08-crisis-management-for-products.md)

*Severity levels, defined by customer impact*

| Sev | Definition | Response | Comms | Postmortem |
|---|---|---|---|---|
| **Sev-1** | Data loss, money moved wrongly, security breach, or total unavailability | Immediate, all hands, incident commander named | Status page within 30 min; direct contact with affected customers | Mandatory, published |
| **Sev-2** | Major function broken for a segment; incorrect output at scale; no data loss | Within 1 hour, business hours or on-call | Status page; proactive email to affected accounts | Mandatory, published |
| **Sev-3** | Degraded or broken for a minority; workaround exists | Next business day | In-app or support macro | Optional |
| **Sev-4** | Cosmetic or minor | Normal backlog | None | No |

### [09 · Career Growth: IC to Director/VP](level-4/09-career-growth-ic-to-director-vp.md)

*The transitions*

| Transition | The real change | Must stop | New skill | Failure mode |
|---|---|---|---|---|
| **PM → Senior PM** | From executing a defined problem to choosing which problem | Waiting to be assigned | Judgement under ambiguity | Staying busy on well-defined work |
| **Senior PM → Staff / Group PM** | From your product to a portfolio, or to a problem too hard for one team | Doing the PM work yourself | Influence without authority; developing others | Becoming a super-PM across three teams |
| **Group PM → Director** | From influencing to owning outcomes and people | Being the best PM in the room | Hiring, performance management, strategy for an area | Managing the work instead of the people |
| **Director → VP** | From an area to the whole org and the company's product strategy | Making the calls your Directors should make | Org design, exec peering, board communication | Becoming a scheduler with no product point of view |
| **VP → CPO** | From product org to company strategy alongside the CEO | Thinking of product as your function | Company-level allocation, commercial ownership | Advocating for product against the company |

### [10 · Capstone — Full Product Strategy + Org Design](level-4/10-capstone-strategy-org-design.md)

*What the deliverable contains*

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

Go deeper with the full [Product Manager Mastery Path](index.md) curriculum or test yourself with the [interview questions](interview-questions.md).
