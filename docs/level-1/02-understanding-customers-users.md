# 02 · Understanding Customers & Users

Everything a PM prioritizes, writes, and ships is downstream of one thing:
how well they actually understand the people using the product. This module
covers the three core tools for building that understanding — customer
interviews, personas, and Jobs-to-be-Done — and how they fit together rather
than compete as alternatives.

## Customer interviews

A good interview surfaces what someone actually *did* and *struggled with*,
not what they *think they'd want*. The single biggest beginner mistake is
asking leading, hypothetical questions ("Would you use a feature that lets
you X?") — people are unreliable predictors of their own future behavior, but
reliable narrators of their past behavior.

| Bad question (hypothetical/leading) | Better question (behavioral) |
|---|---|
| "Would you use a dashboard that shows X?" | "Walk me through the last time you needed to check X — what did you do?" |
| "Do you think notifications are annoying?" | "Tell me about the last notification you got from this product. What did you do with it?" |
| "Would a cheaper plan make you buy more?" | "What made you choose your current plan over the others?" |
| "Do you want more customization options?" | "Tell me about a time the default setup didn't work for you. What did you do?" |

A reliable interview structure:

1. **Warm-up** — context about them and their role/workflow (2-3 min).
2. **Recent, specific story** — "tell me about the last time you [did the
   task related to your research question]" (10-15 min, most of the value).
2b. **Follow the emotion** — when they mention frustration, confusion, or
    relief, dig in: "why was that frustrating?", "what did you try instead?"
3. **Wrap-up** — anything else they'd want you to know; thank them.

!!! tip "Five is often enough to spot a pattern"
    You don't need 50 interviews to act. Once 4-5 people independently
    describe the same underlying problem in their own words, you likely have
    a real, general pattern rather than one person's idiosyncrasy —
    especially if they come from different accounts, segments, or use cases.

## Personas — and their limits

A persona is a composite sketch of a user type, built from real research,
used to keep a team's mental model of "who we're building for" consistent.

| Persona field | Example: "Efficiency Erin" |
|---|---|
| Role/context | Ops manager at a 50-person logistics company |
| Primary goal | Get her team's weekly reporting done in under an hour |
| Key frustration | Has to manually reconcile data from three different tools |
| Technical comfort | Medium — comfortable with spreadsheets, not with APIs |
| What "success" looks like to her | One dashboard she trusts enough to stop double-checking manually |

Personas are useful as **shared shorthand** ("would Erin actually use this
button?") but dangerous if they calcify into stereotypes disconnected from
updated research, or if a team has so many personas that "for whom" stops
meaning anything. Keep the persona list short (2-4 for most products) and
revisit it whenever new research contradicts it.

## Jobs-to-be-Done (JTBD) — the basics

Where personas describe *who*, Jobs-to-be-Done describes *why* someone
"hires" a product — the underlying progress they're trying to make in a
specific situation, independent of any particular solution.

The classic framing: **"When [situation], I want to [motivation], so I can
[expected outcome]."**

| Situation | Motivation | Expected outcome |
|---|---|---|
| When I'm reviewing my team's work at the end of the week | I want to quickly see who's behind on tasks | so I can flag it before Monday's meeting, not during it |
| When a customer complains on a call | I want to pull their account history instantly | so I can sound informed, not caught off guard |

The power of JTBD is that it explains *why customers switch* between products
that look completely different on the surface — a paper planner, a phone
reminder app, and a project-management tool can all be "hired" for the same
underlying job ("make sure I don't forget something important"), which is
why your real competition is often not who you'd assume.

## How these three fit together

- **Interviews** are the raw research method — the actual conversations.
- **JTBD** is the *lens* you apply while listening, to find the underlying
  motivation behind a stated request.
- **Personas** are the *output artifact* you build afterward, to keep the
  whole team aligned on who and what job you heard about.

Skipping interviews and jumping straight to writing personas from guesswork
is the most common failure mode — it produces confident-sounding personas
built on assumptions, which is often worse than no persona at all because it
creates false certainty.

## Worked example

A team building an expense-reporting tool interviews five customers and
hears, in different words, the same story: employees don't submit expenses
promptly because "the app makes me hunt for the right project code every
time." Framed as JTBD: *"When I've just paid for something out of pocket, I
want to log it before I forget the details, so I can get reimbursed without
a scramble at month-end."* The persona built from this pattern — "Traveling
Tom," a mid-level employee who travels twice a month — helps the team keep
that motivation in mind for every subsequent design and prioritization
decision, instead of designing for an imagined "power user who loves
detailed categorization," which none of the five interviewees resembled.

## Exercise

Recruit (or imagine, if you're practicing solo) three people who use a
product or workflow you're curious about. Conduct a short interview with
each using the behavioral-question structure above — focus on one recent,
specific story per person. Then:

1. Write one JTBD statement ("When... I want to... so I can...") that
   captures the shared motivation across at least two of the three.
2. Sketch a one-page persona informed by what you heard, using the fields
   in the persona table above.
