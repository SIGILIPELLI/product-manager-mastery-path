# 07 · Metrics & KPIs Basics

A PRD's "success metrics" section (Module 5) only works if you know how to
choose good metrics in the first place. This module covers the North Star
metric concept and the AARRR ("pirate metrics") framework — two
complementary tools for deciding what to measure and why.

## North Star metric

A North Star metric is the single measure that best captures the core value
a product delivers to its users — chosen so that, if it goes up, the
business is healthier, and every team can trace their work back to
influencing it.

A good North Star metric is a **leading** indicator of value delivered, not
just a **lagging** business outcome like revenue (which is affected by too
many outside factors to guide day-to-day product decisions).

| Product | Weak North Star (lagging/vague) | Better North Star (leading, specific) |
|---|---|---|
| Music streaming app | Total revenue | Weekly hours of music listened per active user |
| Project-management SaaS | Total signups | Number of teams with 3+ active weekly users |
| Ride-sharing app | Total rides | Weekly active riders who complete a ride |
| Photo-editing app | Downloads | Monthly active users who export/share an edited photo |

Notice each "better" version ties directly to the moment the user actually
gets value — not just adjacent activity (a signup isn't value delivered; a
completed ride is).

## AARRR — the "pirate metrics" funnel

AARRR breaks the user lifecycle into five stages, giving you a metric to
track — and a bottleneck to look for — at each one.

| Stage | Question it answers | Example metric |
|---|---|---|
| **A**cquisition | How do users find us? | Signups by channel per week |
| **A**ctivation | Do new users have a good first experience? | % of signups who complete onboarding / reach "first value" moment |
| **R**etention | Do users come back? | % of users active in week 2 who were also active in week 1 |
| **R**eferral | Do users bring others? | % of active users who invite at least one teammate |
| **R**evenue | Do users pay (or convert to paid)? | Free-to-paid conversion rate |

The value of AARRR is diagnostic: if overall growth stalls, this funnel lets
you localize *where* — a product with strong acquisition but weak activation
has a fundamentally different problem (and fix) than one with strong
activation but weak retention.

## Leading vs. lagging metrics

| Type | Definition | Example | Use for |
|---|---|---|---|
| **Leading** | Predicts future outcomes; you can act on it now | Weekly active users, onboarding completion rate | Day-to-day product decisions |
| **Lagging** | Confirms past outcomes; useful for reporting, less for steering | Quarterly revenue, churn rate (measured after the fact) | Business reporting, board updates |

A common mistake is a team obsessing over a lagging metric (like quarterly
churn) week to week — by the time it moves, the decisions that caused the
move are months old. Track leading metrics for steering; report lagging
metrics for context.

## Choosing metrics for a specific initiative

Every PRD needs its own success metrics, distinct from (but ideally
contributing to) the company's North Star. A simple checklist:

| Question | Why it matters |
|---|---|
| Can we actually measure this with existing instrumentation? | An unmeasurable metric can't confirm success |
| Is there a clear baseline before launch? | Without a baseline, "improvement" is unfalsifiable |
| Does moving this metric plausibly move the North Star? | Prevents optimizing a vanity metric disconnected from real value |
| What's a specific, numeric target (not just "improve")? | "Improve engagement" isn't checkable; "+10% week-2 retention" is |

## Worked example

A project-management SaaS's North Star is "teams with 3+ weekly active
users." The team notices Retention (AARRR) is the weak link: strong signups
and activation, but only 35% of teams stay active past week 3. Digging in
with interviews (Module 2), they learn teams stop returning once the initial
project setup is "done" — there's no ongoing reason to open the tool
mid-week. They prioritize (Module 4) a "weekly digest email" initiative
whose PRD (Module 5) sets a specific success metric: "+8 percentage points
in week-3 team retention within 6 weeks of launch, measured against the
current 35% baseline" — a leading, specific, measurable target that plainly
ties back to the North Star.

## Exercise

For the initiative you've been building a PRD around (Modules 3-6), write:

1. A proposed **North Star metric** for the overall product it belongs to
   (even if you're inventing the product context) — and one sentence on why
   it's leading rather than lagging.
2. Which **AARRR stage** your initiative most directly targets, and why.
3. A specific, numeric **success metric** for the initiative itself,
   including a stated baseline and target (estimate plausibly if you don't
   have real data, but state your baseline assumption explicitly).
