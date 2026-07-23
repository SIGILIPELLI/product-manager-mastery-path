# 03 · Problem Discovery

Discovery is the work of figuring out whether a problem is real, big enough
to matter, and worth solving before any design or engineering time is spent.
The single most common cause of wasted product work isn't bad execution —
it's building a well-crafted solution to a problem that wasn't real, wasn't
significant, or wasn't understood correctly in the first place.

## Signals vs. problems

A **signal** is a piece of raw evidence — a support ticket, a churn comment,
a stakeholder request, a metric drop. A **problem** is the underlying,
validated pain that a cluster of signals points to. Confusing the two leads
to building whatever was most recently or loudly requested, rather than what
actually matters most.

| Signal (raw, as received) | Possible underlying problem (needs validation) |
|---|---|
| "Add a dark mode" (one support ticket) | Might be a genuine accessibility/eye-strain issue, or one vocal user's preference |
| Churn spiked 15% this month | Could be onboarding, pricing, a competitor launch, or a bug — undetermined until investigated |
| "Sales says three deals were lost because we lack SSO" | Likely a real, quantifiable problem — but confirm it's not one deal's excuse |
| Weekly active users flat for two quarters | Vague; could be dozens of different underlying causes |

The discovery job is converting the left column into validated, specific
right-column statements — and being willing to conclude "not a real problem"
or "real but too small to prioritize" for some signals.

## Writing a good problem statement

A problem statement should be specific enough that two different people
reading it would design roughly similar solutions — vague problem statements
produce scattered, mismatched solutions.

**Template:**

> **[Who]** is experiencing **[what pain]** when **[in what situation]**,
> which causes **[what consequence]**. We know this because **[evidence]**.

| Weak version | Strong version |
|---|---|
| "Users find onboarding confusing." | "New team admins abandon setup within the first session when they reach the permissions step, because the roles shown don't map to their company's actual job titles — causing 30% of new workspaces to never invite a second user. We know this from session replays (18 of 20 reviewed) and 4 support tickets in the last month." |
| "The app is slow." | "Users on the reports page wait 8-12 seconds for data to load when their date range exceeds 90 days, causing them to abandon the report and email support asking for a CSV instead. Confirmed via APM traces and 6 support tickets over 2 weeks." |

Notice the strong versions name a specific user segment, a specific trigger
condition, a specific consequence, and cite evidence — all four are what
make a problem statement actionable rather than a vague vibe.

## Opportunity sizing — is this worth solving?

Before committing resources, do a lightweight sizing pass. You don't need
perfect data — a rough estimate is enough to decide if something is a top-3
problem or a "note and revisit" one.

| Sizing question | Example answer |
|---|---|
| How many users/accounts does this affect? | ~18% of new workspaces (from onboarding funnel data) |
| What's the business impact if unsolved? | Est. $240K ARR at risk annually from workspaces that never activate a second seat |
| How confident are we this is the real cause (not a symptom of something else)? | Medium-high — confirmed via replays, not just a hunch |
| What's the cost of investigating further vs. acting now? | Low — a fix is estimated at 1 sprint; further research would take a week and add limited certainty |

## A discovery workflow that avoids solution-jumping

1. **Collect signals** for 1-2 weeks without committing to a fix (tickets,
   interview notes, metrics, sales/CS feedback).
2. **Cluster** signals that seem to point at the same underlying issue.
3. **Validate** the top 2-3 clusters with a handful of targeted interviews or
   a data pull — confirm they're real and roughly how big.
4. **Write the problem statement** using the template above, before anyone
   proposes a specific solution.
5. **Only then** move to prioritization (Module 4) and solutioning.

Teams that skip steps 1-4 and go straight from "a stakeholder said X" to "an
engineer is now building X" are the most common source of shipped features
nobody uses.

## Worked example

A B2B analytics tool sees three loosely related signals in one month: two
support tickets about "can't find last month's report," a 12% drop in
7-day-return rate for new accounts, and a sales rep mentioning a lost renewal
citing "we forgot the tool existed." Rather than jumping to "build a
notification feature" (the first solution that comes to mind), the PM
clusters these as possibly one problem, interviews three at-risk accounts,
and confirms: users only think to open the tool when something prompts them
— there's no passive reason to return between report cycles. The validated
problem statement: *"Monthly-cadence users have no reason to return to the
product between report cycles, causing them to forget it exists and consider
it 'not sticky' at renewal time. Confirmed via 3 interviews and a 12%
7-day-return drop concentrated in monthly-cadence accounts."* Only after this
statement exists does the team start considering solutions (a scheduled
digest email, a Slack integration, etc.) — solutioning is deliberately
deferred to Module 4/5.

## Exercise

Pick a product with a public app store or review page (or one you use
yourself). Find three real complaints or reviews that describe a problem
vaguely. For one cluster of related complaints, write a full problem
statement using the template above — you can estimate the evidence/consequence
plausibly if you don't have real analytics access, but be explicit about
which parts are assumptions versus confirmed facts.
