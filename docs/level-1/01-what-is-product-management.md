# 01 · What Is Product Management?

Product management is often described in a one-liner — "the intersection of
business, technology, and user experience" — but that phrase tells you almost
nothing about what a PM actually does on a Tuesday. This module grounds the
role in concrete responsibilities, draws clear lines against adjacent roles
people often confuse it with, and walks through a realistic day so the rest
of this course has a shared reference point for "the job."

## What a PM is actually responsible for

At its core, product management is the discipline of deciding **what** gets
built and **why**, so that engineering can focus on **how**. A PM doesn't
write the code, doesn't (usually) draw the pixels, and doesn't manage
engineers' performance reviews — but they are accountable for the outcome of
the product in a way no one else on the team is.

| Responsibility | What it looks like day to day |
|---|---|
| Understanding the customer | Interviews, support ticket review, usage data analysis |
| Defining the problem | Turning vague pain ("users churn a lot") into a specific, testable problem statement |
| Setting priorities | Deciding what the team works on next, and — just as importantly — what it doesn't |
| Writing requirements | PRDs, user stories, acceptance criteria that engineering and design can build from |
| Aligning stakeholders | Getting sales, support, leadership, and legal rowing in the same direction |
| Measuring outcomes | Defining success metrics before launch, checking them after |
| Making the tradeoff calls | Speed vs. quality, scope vs. deadline, one segment's needs vs. another's |

The common thread: a PM is the person who holds the "why" of the product,
and translates business and customer needs into a plan the rest of the team
can execute against.

## PM vs. Project Manager vs. Designer

These three roles get mixed up constantly, including by companies that hire
for them, so it's worth being precise.

| Role | Owns | Core question |
|---|---|---|
| **Product Manager** | The "what" and "why" — the product's direction, priorities, and success criteria | "Should we build this, and why does it matter?" |
| **Project Manager** | The "when" and "how it gets coordinated" — timelines, dependencies, resourcing | "Is this on track, and what's blocking it?" |
| **Designer (UX/Product Design)** | The "how it feels/works" — flows, interactions, visual and interaction design | "What's the best experience for solving this?" |

A useful shorthand: if a decision is about **whether** to build something,
that's a PM call. If it's about **when** it ships relative to other work,
that's a project manager (or PM wearing a PM-ops hat at smaller companies).
If it's about **how the user experiences** it, that's design — with the PM
and designer collaborating closely, since the "why" constrains the "how."

Many companies (especially startups) don't have dedicated project managers,
so PMs absorb some project-management work. That's a company-size reality,
not a redefinition of the PM role itself — the "why" is still what makes
someone a PM.

## A day in the life

There's no single "typical day" in product management — that's part of the
job's nature — but most days are some mix of:

- **Meetings that gather information**: user interviews, support escalations,
  sales calls to understand a deal blocker, data reviews with analytics.
- **Meetings that align people**: sprint planning, design reviews, roadmap
  syncs with leadership, cross-functional standups.
- **Solo "thinking and writing" time**: drafting a PRD, writing up interview
  notes, building a prioritization model, preparing a stakeholder update.
- **Reactive firefighting**: an incident affecting customers, a sales deal
  that needs a scoping answer today, a metric that dropped and needs
  investigating.

The ratio shifts by company stage — an early-stage startup PM might spend 40%
of their time talking directly to users; a PM at a large company with a
mature product might spend more time on internal alignment and data analysis
because the org itself is more complex to navigate than the problem space.

## Worked example: a mid-sized SaaS company

Consider a PM on a project-management SaaS product's "Notifications" area.
Their week might look like:

- **Monday**: Review weekend support tickets tagged `notifications` — three
  users complained about duplicate email digests. Flag as a discovery input.
- **Tuesday**: 30-minute interview with a user who churned last month, partly
  citing notification overload. Take notes, look for the pattern vs. an
  isolated complaint.
- **Wednesday**: Write a one-page problem statement on notification overload,
  informed by both signals, and bring it to the weekly prioritization
  meeting — where it competes against two other proposed initiatives for the
  same two-engineer team's next sprint.
- **Thursday**: Draft a PRD for the top-prioritized fix (a digest-frequency
  setting), including acceptance criteria, and review it with the engineering
  lead and designer.
- **Friday**: Present the plan and expected impact (using an AARRR-style
  retention metric) to the head of product in the weekly roadmap sync.

Notice what didn't happen: the PM didn't write any code, didn't finalize any
pixel-level design, and didn't build the sprint timeline themselves (the
engineering lead did that, informed by the PRD). What the PM did was turn a
noisy signal into a defined, prioritized, buildable plan — that's the job.

## Exercise

Pick a product you use regularly (a to-do app, a food delivery app, a game —
anything). Write three short lists:

1. **Three decisions** you think a PM on that product would own (what to
   build, what problem to solve, what to deprioritize).
2. **Three decisions** you think belong to a project manager or engineering
   lead instead (timeline, staffing, technical implementation approach).
3. **Three decisions** you think belong to a designer (a specific flow, a
   visual treatment, an interaction pattern).

For each item, write one sentence justifying why it belongs in that bucket
rather than another — this is the exact kind of boundary-drawing you'll do
constantly once you're doing the job for real.
