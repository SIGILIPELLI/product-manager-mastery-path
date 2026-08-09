# 06 · Working with Sales & Customer Success

Sales and customer success are simultaneously your best discovery channel
and the biggest single source of roadmap distortion. They talk to more
customers in a week than you will in a quarter. They also operate on
incentives that are not yours: a rep is paid this quarter for a deal that
closes this quarter, and a CSM is measured on a renewal that lands in six
weeks. Neither is paid for whether the thing they asked for was the right
thing to build.

The failure mode is not that sales is pushy. It is that product has no
**process** — so requests arrive as escalations, get decided by whoever
escalates hardest, and the roadmap becomes a record of which conversations
were most uncomfortable. The fix is unglamorous and completely reliable:
publish an intake process, apply consistent arithmetic to every request, and
report back on everything you decline.

## The tension, stated honestly

| | Sales | Customer Success | Product |
|---|---|---|---|
| **Paid on** | Bookings this quarter | Renewal and expansion | Outcomes over years |
| **Time horizon** | 30–90 days | 90–365 days | 1–3 years |
| **Sees** | Deals that nearly closed | Customers at risk now | The whole system |
| **Systematically over-weights** | The last deal lost | The loudest at-risk account | Its own strategy |
| **Systematically under-weights** | Whether the feature was the real blocker | Accounts that quietly renew | Revenue in flight |

Every column has a real blind spot, including yours. The process below is
designed to correct all three, not just theirs.

## Intake: one door, one format

Requests that arrive by Slack DM, hallway, or a forwarded customer email are
untriageable and unfair — they reward proximity. Publish a single intake
form and refuse to process anything else. Six required fields:

| Field | Why it's required | Rejection rule |
|---|---|---|
| **Account(s) and deal stage** | Turns anecdote into revenue | No account named → returned |
| **ARR at stake** | Enables weighting | "Big" is not a number |
| **The problem, in the customer's words** | Separates problem from proposed solution | "They want a dropdown" → returned |
| **Is this the actual blocker?** | The single most inflated claim in B2B | Rep must state what else is unresolved |
| **What they do today instead** | Reveals the real cost | Blank → the pain may be theoretical |
| **What happens if we say no** | Forces honesty | "We lose the deal" needs evidence |

Two rules that make this stick: **the form takes under three minutes**, and
**every submission gets a written answer within ten working days**, including
the ones you decline. A no with a reason is fine. Silence is what makes
people escalate.

## Triage arithmetic

Attached pipeline is the number sales will quote you, and it is always the
gross figure. Two discounts convert it into something decision-grade:

```
Expected ARR = Attached pipeline
             × P(deal closes | we build it)
             × P(this feature is the true blocker)
```

The second term is the one nobody applies, and it is where most of the
inflation lives. Estimate it from win/loss data, not from the rep's opinion:
if 7 deals cited a custom report builder and 5 of them were also unresolved
on price, the feature was the true blocker in maybe a quarter of cases.

Then rank by **expected ARR per engineer-week**, exactly as in Module 4.

## Worked example — ListUp's Q2 request triage

Thirty-four requests arrived in the quarter, deduplicated to **six themes**.
Engineering capacity available for GTM-driven work: **16 engineer-weeks**
(20% of the quarter's total, a standing allocation agreed at planning).

| Theme | Deals | Attached pipeline | P(close) | P(true blocker) | Eng-wks | Expected ARR | **EV/wk** |
|---|---|---|---|---|---|---|---|
| Multi-account agency console | 9 | $196,000 | 0.55 | 0.85 | 10 | $91,630 | **$9,163** |
| Two more marketplace channels | 4 | $86,000 | 0.60 | 0.90 | 6 | $46,440 | **$7,740** |
| SSO / SAML | 5 | $124,000 | 0.45 | 0.70 | 8 | $39,060 | $4,882 |
| Bulk rule import | 6 | $41,000 | 0.50 | 0.30 | 2 | $6,150 | $3,075 |
| White-label branding | 3 | $52,000 | 0.35 | 0.55 | 7 | $10,010 | $1,430 |
| Custom report builder | 7 | $148,000 | 0.40 | 0.25 | 12 | $14,800 | $1,233 |
| **Total** | **34** | **$647,000** | | | **45** | **$208,090** | |

Three things fall out of this table that no amount of discussion would have
produced:

1. **$647,000 of "at-risk revenue" is really $208,090** — 32.2% of the
   headline. That gap is not dishonesty; it is what happens when you sum
   gross pipeline across overlapping deals.
2. **The custom report builder has the second-largest attached pipeline and
   ranks last.** Seven deals cited it, but win/loss showed only two where it
   was the sole open issue, and it is the most expensive item on the list.
3. **16 weeks of capacity funds the top two** (10 + 6 = 16 exactly),
   capturing $138,070 of the $208,090 — **66% of the expected value for 36%
   of the requested effort.**

**The decisions, published to sales and CS the same week:**

| Theme | Decision | Message to the field |
|---|---|---|
| Agency console | Build, Q2 | Ships week 9; two design partners named; demo available from week 6 |
| Two more channels | Build, Q2 | Ships week 13; sequenced by attached pipeline |
| SSO / SAML | **Q3, committed** | Not this quarter. Interim: IP allowlisting plus enforced 2FA satisfies 3 of the 5 security reviews — here is the written answer to use |
| Bulk rule import | Q3, small | Cheap and useful; parked only because capacity is exhausted |
| White-label branding | No, for 12 months | Strategy non-goal; agencies want a console, not our logo removed. Revisit only if it appears in 8+ deals |
| Custom report builder | **No** | The read API (Module 3) plus a partner analytics app covers 5 of the 7 deals. Here is the partner and the price |

Note what the last two rows do: a **no** with a substitute is a workable
answer for a rep, and a no without one is an invitation to escalate. Half
the value of triage is the workaround column.

Note also that SSO was declared a strategy non-goal until Q3 in Module 1 —
and the triage arithmetic independently placed it third, outside capacity.
When strategy and arithmetic agree, the conversation is short. When they
disagree, that is real information about the strategy, and you should say so
rather than quietly overriding one with the other.

## The commitment log

Anything promised to a named customer with a date is a contract, whatever
the deck says. Keep one log, owned by product:

| Account | Commitment | Date promised | Deal value | Sales owner | PM sign-off | Status |
|---|---|---|---|---|---|---|
| Northgate Agency | Multi-account console, ≥25 sub-accounts | 31 May | $59,700 | R. Okafor | Yes | On track |
| Delaney Retail | SSO via SAML | 30 Sep | $34,000 | R. Okafor | Yes | Q3 planned |
| Two Rivers | Custom report builder | 15 Apr | $22,000 | (unsigned) | **No** | **Retracted** — partner app offered |

The third row is the reason the log exists. A commitment made without PM
sign-off gets retracted early and directly, with the PM on the call. That
is uncomfortable once. Discovering it three weeks before the deadline is
uncomfortable for a quarter.

**Rule of thumb:** more than three open committed items per quarter and you
are running a consultancy with a product-shaped brochure.

## What each side owes the other

Write this as a two-way agreement, not a set of product rules:

| Product owes GTM | GTM owes Product |
|---|---|
| A written answer to every request in 10 working days | All requests through the intake form, with the six fields |
| The declined list with reasons, every quarter | Honest P(true blocker), not the optimistic one |
| A rolling 6-month outlook, refreshed monthly | Win/loss recorded within 5 days of a deal closing |
| Enablement before GA, not after | No roadmap commitment without PM sign-off |
| Known limitations, in writing | The PM in 4 customer calls a month |
| The workaround when the answer is no | Telling product when a workaround stops working |

## Using CS as a discovery instrument

CS sees the failure modes your analytics cannot: workarounds, spreadsheets,
and the reason someone quietly stopped using a feature. Extract it
systematically rather than waiting for escalations.

| Ritual | Cadence | Output for product |
|---|---|---|
| **Churn post-mortem** | Every churned account over $79/mo | A one-paragraph cause, categorised; product owns the category taxonomy |
| **Ticket theme review** | Monthly | Top 10 ticket drivers with volume and hours; candidates for design fixes rather than doc fixes |
| **Save-play review** | Quarterly | What CS says to keep an account — the gaps in what the product says for itself |
| **PM on QBRs** | 2 per month, silent listener | Unfiltered exposure to how customers talk about value |
| **Onboarding shadowing** | 1 per month | Where new accounts stall, before analytics shows it as churn |

**One high-value pattern:** whenever CS builds a spreadsheet, a macro or a
saved query to serve customers, that is an unbuilt feature with a known
audience and a measurable cost. ListUp's agency console originated exactly
this way — a CSM was manually producing a cross-account status sheet for
four agencies every Monday, about 5 hours a week. That artefact is stronger
evidence than any request form, because someone was already paying for it in
labour.

## Handling the escalation you cannot win

Sometimes a genuinely large customer wants something genuinely wrong for the
product. Four options, in order of preference:

| Option | When | Cost |
|---|---|---|
| **Substitute** — solve the underlying problem differently | The request is a proposed solution, not a problem | Discovery time; usually the best outcome |
| **Sequence** — commit to a date further out | It's on the roadmap anyway | A dated commitment you must honour |
| **Partner** — a third party solves it | Adjacent to your strategy | Ecosystem management (Module 3) |
| **Decline and price the consequence** | It contradicts the strategy | Say the number out loud: "this is $59,700 of ARR we are choosing to risk, and here is why" |

The fourth option is legitimate and underused. Executives can accept losing
a deal on purpose. What they cannot accept is discovering it happened by
accident.

## Exercise

1. **Design the intake form** with your six required fields, and write the
   rejection rule for each. Publish it and route one existing Slack request
   through it.
2. **Triage a real quarter.** Take every request from the last 90 days,
   dedupe to themes, and build the full table: deals, attached pipeline,
   P(close), P(true blocker), engineer-weeks, expected ARR, EV per week.
3. **Estimate P(true blocker) from win/loss data**, not opinion. For your
   largest theme, count how many cited deals had other unresolved issues.
   Report the gap between gross attached pipeline and expected ARR as a
   percentage.
4. **Set a standing capacity allocation** for GTM-driven work as a
   percentage of the quarter, get it agreed at planning, and draw the line
   on your ranked table where capacity runs out.
5. **Write the decision table** including a workaround or substitute for
   every "no". Any "no" without one goes back for another pass.
6. **Build the commitment log** with every open promise to a named customer.
   Count them, flag any without PM sign-off, and schedule the retraction
   conversations this week.
7. **Draft the two-way agreement** — what product owes GTM and what GTM owes
   product — and get both leaders to sign it.
8. **Find one CS spreadsheet.** Identify a manual artefact CS maintains,
   measure the hours per week it costs, and write it up as a feature brief
   with that number as the evidence.
