---
status: canonical
last-reviewed: 2026-05-26
review-trigger: workflow changes
---

# Contributing — How we work

This is the operations manual. Read it once when you start, then refer back when a question comes up.

## Frontmatter convention

Every doc except `CLAUDE.md`, `ROADMAP.md`, and the `_template.md` files carries frontmatter:

```yaml
---
status: <draft | active | canonical | archived>
last-reviewed: <YYYY-MM-DD>
review-trigger: <what makes this doc stale>
---
```

- **status** — current state of the doc itself
- **last-reviewed** — update when you touch the doc, even just to confirm it's still accurate
- **review-trigger** — what change in the world should force a re-review (e.g. "when we ship onboarding," "when the data model changes")

## The work model

Three sizes of work. Pick the right one before starting.

### Phases — multi-task design work

Open one or two at a time. A phase has a thesis (the structural change it delivers), workstreams (lettered A, B, C), an opening checklist, a decisions log, and a closing checklist. Lives in `docs/phases/<phase-name>.md`. Use `_template.md`.

Phases aren't time-boxed — one might run an afternoon, another might stretch across many days. What's consistent is the rhythm:

1. **Plan.** Sketch workstreams, name dependencies, tighten the thesis. Mostly writing — the thinking that makes the build cheaper.
2. **Build.** Execute the workstreams. Capture decisions in the phase board's decisions log as they happen.
3. **Review.** The longest step. Claude generates a walkthrough — a streamlined checklist of what to verify, with context on where to look, what to do, and what to expect. You go through it manually, slow and deliberate. The checklist revises as items get checked off; a decisions log at the end captures anything new that surfaced (unless already documented elsewhere). This is where most of the project's intelligence lands — tasks for the punch list and ideas for the next phase show up here, not during the build. For designers especially, this is the moment to step out of the build conversation and into slower craft — evaluate, compare, tinker, open Figma if it helps.

Phases close when their thesis is delivered. Closing produces: updated feature docs, decisions log entries, ROADMAP update, CLAUDE.md update, and the phase board archived to `docs/archive/phases/`.

### Side tasks — ~30min to a few hours, focused

For work that doesn't fit a phase board: between phases, alongside an active phase, or surfaced from an unrelated investigation. Lands as one PR. Updates only the feature docs it touches. Does NOT modify CLAUDE.md, ROADMAP, phase boards, or the open-questions log.

Default for "should I resume a paused phase?" is **no — ask the user first.**

### Punch list — ≤30min isolated fixes

For UI tweaks, copy edits, small bugs. Lives in `docs/phases/punch-list.md`. Each item is numbered (P1, P2, ...) with a one-liner + status. Work from the file in any session.

## Decision tree

"I noticed something we should do. Where does it go?"

```
Is it 30 minutes or less, isolated, no design discussion needed?
  → Punch list

Is it 30min–few-hour focused work, one-PR-shaped, no strategic implication?
  → Side task

Is it multi-task work with a structural thesis, multiple decisions to make,
  or coupling across surfaces?
  → New phase (or addition to active phase if it's on-thesis)

Is it strategic, unresolved, needs a decision before we can act?
  → Open questions log
```

## Opening a phase

Before opening, the user should agree this is the right next phase. (If the roadmap already names it, that's the agreement.)

1. Create `docs/phases/<phase-name>.md` from `_template.md`.
2. Fill the thesis (one paragraph: what structural change this phase delivers).
3. Fill the Opening Checklist:
   - List the strategy docs to read before starting
   - List the open questions to check
   - List the feature / implementation docs likely to be touched
4. Sketch workstreams A, B, C — initial scope, ordered by dependency.
5. Update `CLAUDE.md` → Current Phase section.
6. Update `docs/ROADMAP.md` — move the phase from Upcoming to Active.
7. Tell the user the phase is open and you're ready to start.

## Closing a phase

When the phase thesis is delivered. **A phase close ends the chat session** — do not open the next phase in the same conversation. Context gets heavy, decisions blur, and review discipline weakens when build energy carries forward. The next phase opens in a fresh chat, started by the handoff message you write in step 12.

1. **Show the closing checklist to the user before starting.** Phase close is a high-leverage moment — confirm the list before editing docs.
2. **Walk through the phase board's Decisions log.** Anything load-bearing belongs in `decisions.md`, a feature doc, or a strategy doc — not just the phase board (it's about to be archived).
3. **Update affected feature docs** in `docs/features/`. Add new ones if the phase shipped a new feature.
4. **Update affected implementation docs** in `docs/implementation/`.
5. **Update `docs/strategy/open-questions.md`** — mark resolved, add new, update parked.
6. **Update `docs/decisions.md`** — log non-obvious decisions with dates and reasoning.
7. **Update `docs/ROADMAP.md`** — move phase to Closed, refresh upcoming list.
8. **Update `CLAUDE.md`** — Current Phase points at the next phase (or "between phases"), Strategic Context updated if anything fundamental shifted.
9. **Archive the phase board** — move `docs/phases/<phase-name>.md` → `docs/archive/phases/<phase-name>.md`. Update its frontmatter status to `archived`.
10. **Structural audit** — read CLAUDE.md, ROADMAP, and the strategy docs end-to-end. Anything stale? Trim it.
11. **Evaluate the next candidate.** Review the ROADMAP's Upcoming list, the open-questions log, and recent decisions. Discuss with the user if the call isn't obvious. Recommend one phase to open next.
12. **Write the handoff message.** Compose a short message the user will paste into a new chat to open the next phase. Include: the next phase name + one-line thesis, the strategy docs to read first, the open questions to check, and the workstreams to start with. End the current session here.

## Doc maintenance

- **Touching a doc?** Update `last-reviewed`.
- **Doc is wrong or out of date?** Fix it in the same PR as the work that surfaced it.
- **Doc is unused?** Archive or delete. Stale docs are worse than no docs.
- **CLAUDE.md is the loaded-every-session doc.** Keep it under 200 lines. If it's growing, move history to `decisions.md` and detail to feature/implementation docs.

## Memory and other persistence

- **Claude's memory** is for cross-conversation facts about the user and project that aren't derivable from code or docs. Workflow preferences, user role, project-level constraints that don't fit elsewhere.
- **Phase boards** persist within a phase but don't outlive it (they archive).
- **Decisions log** is the long-term institutional memory of why things are the way they are.
- **Feature docs** describe current state. Decisions describe how we got here.
