# 05 · Writing Requirements

Once an initiative is prioritized, someone has to turn it into something
engineering and design can actually build from. This module covers user
stories (the small, atomic unit of requirement) and PRDs (the document that
ties a set of stories together with context, scope, and success criteria).

## User stories

A user story captures a piece of functionality from the user's point of
view, focused on *why* they want it — not a technical implementation
spec.

**Template:** *As a [type of user], I want to [do some action], so that
[benefit/outcome].*

| Weak story | Strong story |
|---|---|
| "Add a filter dropdown to the reports page." | "As a team lead reviewing weekly reports, I want to filter results by team member, so that I can check one person's numbers without scanning the whole list." |
| "Build an export button." | "As an ops manager, I want to export the current filtered view to CSV, so that I can share results with people who don't have product access." |

The weak versions describe a UI element; the strong versions describe a
need. This matters because it leaves room for design and engineering to
propose a better solution than the one the PM might have imagined (maybe a
saved-filter feature solves the underlying need better than a dropdown) —
while the weak version accidentally locks in a specific implementation as if
it were the requirement itself.

### Acceptance criteria

Every story needs acceptance criteria — the specific, testable conditions
that determine "done." Without these, "done" is a matter of opinion, and
that gap is where scope disagreements happen late in a sprint.

**Format (Given/When/Then works well):**

```
Given a team lead is on the reports page with 15+ team members shown
When they select a specific team member from the new filter
Then only that person's rows are shown, and a "Clear filter" control appears
```

| Story | Acceptance criteria |
|---|---|
| Filter reports by team member | Selecting a name filters the table instantly (no page reload); an active filter shows a visible "Clear filter" chip; filter selection persists if the user navigates away and back within the same session |
| Export filtered view to CSV | Export respects the currently active filter, not the full unfiltered dataset; exported file opens correctly in Excel and Google Sheets; filename includes the export date |

## PRDs — tying stories together

A Product Requirements Document (PRD) is the container that gives a set of
stories shared context: what problem they solve, why now, what's explicitly
out of scope, and how success will be measured. A good PRD is short enough
that engineering and design actually read the whole thing.

**Standard PRD sections:**

| Section | Purpose | Typical length |
|---|---|---|
| Problem statement | The validated problem this solves (from Module 3) | 2-4 sentences |
| Goals / success metrics | What "working" looks like, quantified | 3-5 bullet metrics |
| Non-goals | What's explicitly out of scope, to prevent scope creep | 2-4 bullets |
| User stories | The atomic requirements, with acceptance criteria | As many as needed |
| Open questions | Known unknowns that need an answer before/during build | A running list |
| Launch plan | Rollout approach — full launch, phased, behind a flag | 2-4 sentences |

!!! tip "Non-goals earn their place in every PRD"
    Explicitly writing "this will NOT support X" prevents the single most
    common late-sprint argument: someone assumes a feature is in scope
    because it wasn't explicitly excluded. A blank non-goals section is a
    red flag that scope hasn't actually been thought through.

## Worked example: mini-PRD

**Problem statement:** Team leads reviewing weekly reports on teams of 10+
must manually scan the full table to find one person's numbers, which
several interviews confirmed leads to errors and wasted time (avg. reported
~4 minutes per report review).

**Goals:**
- Reduce time-to-find-one-person's-data to under 15 seconds (baseline: ~4 min)
- No regression in overall reports-page load time

**Non-goals:**
- Multi-person comparison view (tracked separately as a Level 2 candidate)
- Saving named/custom filter presets (out of scope for v1)

**User stories:**
1. As a team lead, I want to filter the report table by team member, so
   that I can check one person's data without scanning the whole list.
   - *AC:* Selecting a name filters instantly; a "Clear filter" chip appears
     when active; selection persists within the session.
2. As a team lead, I want the exported CSV to respect my active filter, so
   that I can share just the relevant subset.
   - *AC:* Export button respects current filter state; filename includes
     export date.

**Open questions:** Should the filter support multi-select (more than one
team member at once) in v1, or is single-select enough to validate the
approach first?

**Launch plan:** Ship behind a feature flag to 20% of accounts for one week,
check the success metric, then roll out to 100%.

## Exercise

Take the top-priority initiative from your Module 4 exercise. Write:

1. **Two user stories** for it, in the "As a... I want... so that..." format.
2. **Acceptance criteria** for each story, using Given/When/Then.
3. A short **non-goals list** (at least 2 items) — things a reasonable
   person might assume are in scope, that you're explicitly excluding.

You'll assemble a full PRD from pieces like these in Module 10's project.
