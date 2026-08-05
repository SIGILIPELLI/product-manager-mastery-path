# 07 · Agile/Scrum for PMs

Scrum is a delivery framework, not a product framework. It tells a team how
to organise two weeks of work; it says almost nothing about whether that
work is worth doing. Which is exactly why PMs get into trouble with it: the
ceremonies fill the calendar, the backlog fills with tickets, and the
quarter ends with a lot of velocity and no outcome. Your job inside Scrum is
narrow and non-negotiable — **own the *why* and the *what*, protect the
team's ownership of the *how*, and make sure every sprint has a goal a
customer would recognise**.

This module covers the roles as they actually work, what a PM does in each
ceremony, how to write stories and acceptance criteria engineers don't have
to interrogate you about, how to read velocity honestly, and when Kanban is
the better answer.

## Roles, honestly

| Role | Owns | In practice |
|---|---|---|
| **Product Manager** | Problem, outcome, strategy, discovery, launch | In smaller orgs, also the PO |
| **Product Owner** | Backlog order, story acceptance, in-sprint clarification | A Scrum role, not a career; often the same person as the PM |
| **Scrum Master / Delivery lead** | Process health, removing impediments | Not your boss and not your assistant |
| **Engineering** | Technical design, estimates, *how* | Estimates are theirs. Full stop |
| **Design** | Interaction and visual solution | Should be in refinement, not handed a spec |

The split that matters: **you set the problem and the boundary; the team
picks the solution inside it.** A PM who specifies implementation gets
compliance instead of engineering judgement, and inherits every technical
consequence personally.

## What a PM actually does in each ceremony

| Ceremony | Cadence | Your job | Failure mode |
|---|---|---|---|
| **Backlog refinement** | Weekly, 60–90 min | Bring the top 2 sprints' items with context and open questions; leave with estimates and a shared understanding | Reading tickets aloud; showing up with unrefined ideas |
| **Sprint planning** | Start of sprint, 1–2h | Propose a sprint *goal*; answer scope questions; accept the team's capacity call | Negotiating estimates down; treating it as a commitment ceremony |
| **Daily standup** | 15 min | Listen; unblock decisions that need you; usually say nothing | Turning it into a status report to you |
| **Sprint review / demo** | End of sprint | Bring stakeholders and real feedback; accept or reject against acceptance criteria | Demoing on the team's behalf; accepting work that misses the AC "to be nice" |
| **Retrospective** | End of sprint | Attend, contribute, don't dominate; own your action items | Skipping it, or defending process you introduced |

If you attend only two, make them refinement and review. Refinement is where
quality gets decided; review is where reality gets checked.

## The sprint goal

A sprint goal is one sentence describing the outcome, independent of which
tickets get done. It's the mechanism that lets the team make sensible
tradeoffs mid-sprint without asking you.

| Weak | Strong |
|---|---|
| "Finish tickets PRD-201 through PRD-214" | "A seller can connect a second marketplace with OAuth and see it confirmed, without leaving ListUp" |
| "Work on the analytics epic" | "Anyone on the team can answer 'how many publishes failed yesterday, and why' from a dashboard" |

Test: if half the tickets slipped but the goal was met, was the sprint a
success? If yes, the goal is real. If not, you wrote a ticket list.

## Stories and acceptance criteria

Use the standard form, and treat **INVEST** as a checklist for splitting:

> As a **[user type]**, I want **[capability]**, so that **[benefit]**.

| INVEST | Test | Common violation |
|---|---|---|
| **I**ndependent | Can it ship without another story? | "Part 2 of 3" chains |
| **N**egotiable | Is the *how* still open? | Story specifies the database schema |
| **V**aluable | Would a user or the business notice? | "Refactor the service layer" as a user story |
| **E**stimable | Does the team know enough to size it? | Unanswered questions in the description |
| **S**mall | Does it fit comfortably in one sprint? | 13+ points |
| **T**estable | Are pass/fail conditions written? | "Should be fast" |

Acceptance criteria in **Given / When / Then** form, covering the unhappy
paths — which is where the sprint actually goes:

| Scenario | Criterion |
|---|---|
| Happy path | **Given** a seller with a connected marketplace, **when** they publish a price change, **then** a preview lists every field that will change per channel before confirmation |
| Empty state | **Given** no fields have changed, **when** they open the preview, **then** it says "nothing will change" and the publish button is disabled |
| Error | **Given** a marketplace API is unreachable, **when** the preview loads, **then** that channel is shown as "status unknown" and publish proceeds for the others |
| Permissions | **Given** a read-only team member, **when** they open the preview, **then** they can view it but cannot confirm |
| Scale | **Given** 500 changed listings, **when** the preview loads, **then** results render within 3 seconds |

**Definition of Ready** (before a story enters a sprint): problem stated,
AC written, design attached if UI, dependencies identified, estimated,
tracking events specified. **Definition of Done** (before it counts):
merged, tested, docs updated, analytics firing and verified, feature-flagged
or released, AC demonstrably met.

## Estimation and capacity

Story points measure **relative size including uncertainty** — not hours.
The team estimates; you don't. Your job is to use velocity correctly.

| Sprint | Committed | Delivered |
|---|---|---|
| 12 | 36 | 32 |
| 13 | 38 | 36 |
| 14 | 34 | 29 |
| 15 | 40 | 38 |
| 16 | 36 | 35 |

Average delivered = 170 ÷ 5 = **34 points**. Range is 29–38, so plan against
34 and communicate the range, never the best sprint.

Capacity for sprint 17, a two-week sprint with 5 engineers:

| Line | Days |
|---|---|
| 5 engineers × 10 working days | 50 |
| − planned PTO | −4 |
| − on-call rotation | −5 |
| **Available engineering days** | **41** |

Then reserve explicitly: with a standing 20% allocation to bugs and tech
debt, **34 × 0.8 ≈ 27 points** are available for new feature work. Making
that reservation visible is one of the highest-leverage things a PM does —
teams that don't reserve it pay it later at a worse exchange rate, and the
PM gets blamed for a "slow team."

Velocity rules: it is a **planning input, not a performance metric**; it is
not comparable between teams; and it collapses the moment anyone is
rewarded for it.

## Scrum or Kanban

| Signal | Scrum | Kanban |
|---|---|---|
| Work arrives | In planned batches | Continuously, unpredictably |
| Typical team | Feature development | Platform, support, growth experiments |
| Planning | Sprint commitment | WIP limits, pull |
| Key metric | Velocity, goal attainment | Cycle time, throughput |
| Release cadence | Per sprint or on demand | Continuous |

If more than about a third of a team's sprint is consumed by unplanned work,
sprint commitments become fiction and Kanban with WIP limits is more honest.
Many teams end up hybrid: Kanban flow with a two-week planning and review
rhythm — which is fine, as long as nobody pretends the velocity chart still
means something.

## Worked example — ListUp sprint 17

**Context:** analytics (Module 4) identified second-marketplace connection
as the constraint; discovery (Module 1) identified API-key retrieval as the
friction; prioritization (Module 2) sequenced sync alerts first, then this.

**Sprint goal:** *A seller can connect a second marketplace via OAuth and
see confirmation, without leaving ListUp or finding an API key.*

**Capacity:** 41 engineering days, 34-point planning velocity, 27 points for
feature work after the 20% reserve.

| Story | Points | Note |
|---|---|---|
| OAuth flow for Marketplace A | 8 | Includes token refresh |
| OAuth flow for Marketplace B | 5 | Reuses A's pattern |
| Connection confirmation state + error handling | 5 | Covers the "status unknown" AC |
| Fall back to manual key entry if OAuth fails | 3 | Non-negotiable — B's OAuth is flaky |
| Instrument `marketplace_connect_started` / `_completed` / `_failed` | 3 | Part of Definition of Done, not optional |
| **Total** | **24** | 3 points under the 27 ceiling, deliberately |

**Mid-sprint reality:** Marketplace B's OAuth returned an undocumented scope
error on day 6. Because the goal was *connect a second marketplace*, not
*ship both integrations*, the team shipped A's OAuth plus the manual
fallback for B and met the goal. Had the sprint been defined as a ticket
list, the same two weeks would have been reported as a failure — and the
fallback story, which is what actually protected the outcome, would have
been the thing cut to "stay on plan."

**At review:** the PM rejected one story — instrumentation fired
`marketplace_connect_completed` for manual key entry as well as OAuth,
making the two paths indistinguishable in analytics. The AC said the events
must be separable. Accepting it would have cost a month of ambiguous data
for one day of rework.

## Exercise

Using your current team and backlog:

1. **Write a sprint goal** for your next sprint in one sentence, and test
   it: if half the tickets slipped, could the goal still be met?
2. **Rewrite three backlog items** as INVEST stories with Given/When/Then
   acceptance criteria covering the happy path plus at least three of:
   empty state, error, permissions, scale.
3. **Draft a Definition of Ready and a Definition of Done** with your team.
   Then audit the current sprint: how many stories entered it not Ready?
4. **Build a capacity table** for the next sprint: engineers × days, minus
   PTO/on-call/support, plus an explicit percentage reserved for bugs and
   tech debt. Show the resulting feature-work capacity to your stakeholders.
5. **Chart the last five sprints' delivered points.** Report the average and
   the range, and rewrite one commitment you've made using the range instead
   of the best-case number.
6. **Score your team's fit** against the Scrum/Kanban table. If more than a
   third of recent sprints was unplanned work, write the case for changing
   the process.
