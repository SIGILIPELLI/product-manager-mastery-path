# 08 · Crisis Management for Products

Every product leader eventually has a day where the product does something
expensive to customers. A pricing bug charges people twice. A migration
loses data. A model auto-applies a change across thousands of catalogues
before anyone notices. The technical fix is usually the easy part and is
usually not yours; what is yours is everything around it — how fast the
organisation notices, who is allowed to decide, what customers are told and
when, and what the company actually learns.

Crises are the highest-leverage hours of your career in both directions.
Customers who experience a well-handled incident often end up *more* loyal
than customers who never had one, because they have now seen how you behave
under pressure. Customers who experience a badly handled one leave and tell
everyone. The difference is almost never the outage length. It is the
communication and the follow-through.

The distinguishing feature of a product crisis, as opposed to an
infrastructure outage, is that **the system is usually working exactly as
built** — it is just doing something wrong at speed and at scale. Nothing is
down. Nothing pages. That is what makes them slow to detect and expensive by
the time they surface.

## Severity levels, defined by customer impact

Severity must be defined by impact, not by engineering effort, and the
definitions must be written before you need them. Arguing about severity
during an incident is a symptom of never having agreed it.

| Sev | Definition | Response | Comms | Postmortem |
|---|---|---|---|---|
| **Sev-1** | Data loss, money moved wrongly, security breach, or total unavailability | Immediate, all hands, incident commander named | Status page within 30 min; direct contact with affected customers | Mandatory, published |
| **Sev-2** | Major function broken for a segment; incorrect output at scale; no data loss | Within 1 hour, business hours or on-call | Status page; proactive email to affected accounts | Mandatory, published |
| **Sev-3** | Degraded or broken for a minority; workaround exists | Next business day | In-app or support macro | Optional |
| **Sev-4** | Cosmetic or minor | Normal backlog | None | No |

Two rules worth fixing in advance:

- **Anyone can declare a Sev-1.** If declaring requires permission, the
  declaration is late every time. Over-declaration is cheap; the cost of
  down-grading an incident an hour in is roughly zero.
- **Incorrect output at scale is a Sev-1 or Sev-2, not a bug.** Product
  crises hide in this category because every dashboard is green.

## Incident roles

Three roles, three different people, always. The most common failure in an
early crisis is one person trying to hold all three, at which point the
customer communication stops for ninety minutes.

| Role | Owns | Does not do |
|---|---|---|
| **Incident commander** | Decisions, sequencing, declaring severity, calling resolution | Debug the code |
| **Comms lead** | Status page, customer emails, support and sales briefing, exec updates | Make technical decisions |
| **Technical lead** | Diagnosis and fix | Talk to customers |
| **Scribe** | Timestamped log of everything, as it happens | Anything else |

The product leader is usually the **comms lead** or, in a large product
crisis with a commercial dimension, the incident commander. Being the
technical lead is almost always the wrong choice even when you are capable
of it, because it is the role that cannot see the whole.

The scribe is the role people cut when short-handed, and it is the one that
determines whether the postmortem is analysis or reconstruction. Timestamps
recovered from memory a day later are worthless.

## Worked example — ListUp's auto-apply incident

**What happened.** A change to Decide's confidence calibration shipped on a
Tuesday. Under a specific condition — SKUs with fewer than five competing
listings — it inflated confidence scores, pushing recommendations above the
0.85 auto-apply threshold that should have gone to the review queue. Prices
were automatically reduced on **214,000 SKUs across 1,900 seller accounts**
for **3 hours 40 minutes**.

Nothing was down. Error rates were flat. No alarm fired. The first signal
was a customer.

**The timeline, from the scribe's log:**

| T+ | Event |
|---|---|
| 0:00 | Calibration change deployed; all health checks green |
| 0:47 | First customer support ticket: "why did my prices drop?" |
| 0:58 | Second and third tickets; support escalates |
| 1:03 | On-call engineer paged |
| 1:11 | **Sev-1 declared**; commander, comms lead, technical lead named |
| 1:18 | Status page: "investigating reports of unexpected price changes" |
| 1:36 | Cause identified; rollback begins |
| 1:44 | Auto-apply globally disabled — the decision that stopped the bleeding |
| 2:14 | Rollback complete; no new incorrect changes |
| 3:40 | All 214,000 affected prices restored to pre-incident values |
| 4:10 | Email to all 1,900 affected accounts with SKU counts and next steps |
| 27:00 | Public postmortem published; per-account impact statements sent |

**The 47-minute detection gap is the incident.** Everything after 1:03 was
competent. The company had no alarm on the *rate of auto-applied changes*,
only on errors and latency — so a system confidently doing the wrong thing
at high volume looked exactly like a system working well.

**The cost:**

| Line | Calculation | Value |
|---|---|---|
| SKUs mispriced | | 214,000 |
| SKUs that transacted during the window | | 41,200 |
| Average order value | | $38.40 |
| Average underpricing | | 26% |
| **Direct merchant loss** | 41,200 × $38.40 × 26% | **$411,341** |
| Average loss per affected account | $411,341 ÷ 1,900 | $216.50 |
| Service credits (one month, all 1,900 accounts) | 1,900 × ($2,957 ÷ 12) | $468,192 |
| **Total direct cost** | | **$879,533** |
| 90-day churn, affected accounts | 6.2% vs 1.8% baseline | 4.4 points |
| Excess churned accounts | 4.4% × 1,900 | 83.6 |
| **Churned ARR** | 83.6 × $2,957 | **$247,205** |
| **Total cost** | | **$1,126,738** |

**The number that should end every argument about guardrail work:** a volume
alarm on auto-applied changes, plus a circuit breaker that halts auto-apply
when the rate exceeds three standard deviations from the trailing hourly
mean, was estimated at **7 engineer-weeks — $26,628**. That is **42 times
cheaper** than the incident it would have caught in under five minutes
instead of forty-seven.

**The decisions that mattered, in order:**

| Decision | Made at | Why it was right |
|---|---|---|
| Disable auto-apply globally, not just for the affected condition | T+1:44 | Stopped the bleeding before the cause was fully understood. Reversible; the alternative was not |
| Restore prices without waiting for customer requests | T+2:14 | Customers should not have to ask to be made whole |
| Reimburse the full $411,341 merchant loss, uncapped | Day 2 | Cheaper than the trust; and capping it would have been the story |
| Publish the postmortem publicly | Day 2 | Channelry's competitive attack was already circulating; the postmortem defused it |
| Re-enable auto-apply only after the circuit breaker shipped | Week 3 | Held the line against commercial pressure to restore the feature |

That last one was the hardest. Auto-apply was disabled for 19 days, during
which Decide's headline value proposition did not work and sales lost two
deals. Re-enabling it early would have been defensible in the moment and
catastrophic if it had recurred. **The credibility of your fix is spent
entirely at the moment you turn the feature back on.**

## Customer communication

| Principle | Practice | Why |
|---|---|---|
| **First, fast, incomplete** | Publish within 30 minutes even with nothing but "we are investigating" | Silence is interpreted as concealment |
| **From a named human** | The comms lead signs it | "The team" is nobody |
| **Specific to them** | Tell each account what happened to *their* data, with counts | Generic notices force customers to do your work |
| **No jargon, no minimising** | "Prices on 214,000 items were reduced in error" | "A brief anomaly" makes people angrier |
| **Make them whole first, negotiate never** | Credits issued proactively | Cost of the credit is far below the cost of the argument |
| **Cadence, then keep it** | "Next update in 30 minutes" — then update in 30 minutes, even with nothing new | The rhythm is the reassurance |
| **Close it explicitly** | A final message saying it is resolved and what changed | Otherwise customers never learn it ended |
| **Never blame a vendor** | Even when it is true | You chose the vendor |

**The update template**, usable in any incident:

> **What is happening:** Prices on some items may have been reduced
> automatically without approval between 09:12 and 12:52 UTC.
>
> **Who is affected:** Sellers using Decide auto-apply. If you do not use
> auto-apply, you are not affected.
>
> **What we have done:** Auto-apply is disabled globally. All affected
> prices have been restored to their pre-incident values.
>
> **What you should do:** Nothing. We will contact every affected account
> individually with the exact items and any revenue impact by 18:00 UTC.
>
> **Next update:** 15:00 UTC, or sooner if anything changes.

Five questions in the reader's order of urgency. Note that "what you should
do: nothing" appears before the explanation of the cause. **Customers want
to know their obligations before they want your diagnosis**, and the reverse
ordering is the single most common flaw in incident communications.

## Internal communication during a crisis

| Audience | Cadence | Content | Common failure |
|---|---|---|---|
| Support | Every 30 min | Approved wording, affected account list, escalation path | Learning about it from customers |
| Sales / CS | Hourly | The same wording, plus what not to promise | Improvising compensation |
| Exec team | Hourly, then daily | Impact, cost, decisions taken, decisions needed | A 40-person incident channel with no summary |
| Whole company | Once, at resolution | What happened, what we are doing | Rumour filling the vacuum |
| Board | Within 24h if material | Cost, cause, prevention, and whether it can recur | Being told at the quarterly meeting |

**Give support the exact wording within 30 minutes.** They are talking to
customers whether or not you have prepared them, and unbriefed support
generates a second crisis of contradictory statements.

## The postmortem

| Element | Requirement |
|---|---|
| **Blameless** | Describe systems and decisions, never individuals. No "who" field |
| **Timestamped** | From the scribe's log, not from memory |
| **Detection first** | Time-to-detect is usually the biggest number and the cheapest to fix |
| **Causal chain, not a root cause** | Real incidents have four or five contributing conditions |
| **Impact quantified** | Customers, records, currency |
| **Actions with owners and dates** | Fewer than six, all funded, tracked to done |
| **Published** | Internally always; externally for Sev-1 |

**ListUp's causal chain**, which is what a real one looks like:

| Condition | Category |
|---|---|
| The calibration change was tested on high-competition SKUs only | Evaluation coverage |
| The evaluation set under-represented SKUs with fewer than five competitors | Data representativeness |
| No per-slice regression bar existed (Level 4, Module 7) | Missing control |
| No alarm on auto-applied change *volume* | Missing detection |
| No circuit breaker on anomalous action rates | Missing containment |
| Support had no path to escalate a pattern of similar tickets in under 45 minutes | Missing signal path |

Six conditions, no villain. Any one of them being absent would have shortened
the incident, and the two cheapest — the volume alarm and the ticket-pattern
escalation path — would have cut the detection gap from 47 minutes to under
five. **"Root cause: human error" is not a finding; it is the point at which
the investigation stopped.**

## The crisis playbook to write before you need it

| Item | Prepared in advance |
|---|---|
| Severity definitions | Written, agreed with support and engineering |
| Who can declare | Anyone, no permission required |
| Role assignments | Named rota, with backups |
| Comms templates | Status page, customer email, support macro |
| Status page access | Comms lead can publish without engineering |
| Customer impact query | A saved query that returns affected accounts fast |
| Credit policy | Pre-approved thresholds so nobody negotiates during an incident |
| Exec escalation | Who to wake, at what severity, by what channel |
| Legal / regulatory triggers | Which incident types require notification, and within how long |
| Postmortem template | Blameless format, action tracker |
| **A rehearsal** | One tabletop exercise per quarter, on a real scenario |

The rehearsal is the row that gets skipped and the one that produces most of
the value. A 45-minute tabletop — "Decide auto-applies wrong prices to 1,900
accounts; go" — reliably finds three broken things: nobody can publish to
the status page without engineering, there is no saved query for affected
accounts, and the credit policy does not exist. Finding those on a Wednesday
afternoon costs nothing. Finding them at T+18 costs an hour of an incident.

## Exercise

1. **Write your severity definitions** in terms of customer impact, and get
   support and engineering to agree them in writing.
2. **Confirm who can declare a Sev-1.** If the answer is not "anyone",
   change it, and say so publicly.
3. **Assign the four roles** with named backups, and check that no one person
   holds two of them.
4. **Take your last significant incident and cost it**: direct customer
   impact, credits, excess churn against baseline, and the total.
5. **Cost the prevention** that would have caught it, in engineer-weeks and
   dollars, and compute the ratio. Take that ratio to your next planning
   meeting.
6. **Measure your time to detect** across the last five incidents. If
   detection is longer than diagnosis plus fix, your problem is
   instrumentation, not engineering.
7. **Write the five-question customer update template** and check the
   ordering — obligations before diagnosis.
8. **Write the pre-approved credit policy** so nobody has to negotiate
   during an incident.
9. **Run a tabletop exercise** this quarter on a realistic product-level
   scenario, and write down every broken thing it uncovers. Fix the two
   cheapest before the next one.
