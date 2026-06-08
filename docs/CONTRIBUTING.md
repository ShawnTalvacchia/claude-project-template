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

## Running a review

Review is the longest, most consequential step inside a phase. The walkthrough is its own doc — `docs/phases/<phase-name>-walkthrough.md`, copied from `_walkthrough-template.md` — paired with the phase board and archived alongside it at close. Don't generate the walkthrough loose in chat, and don't bury it inside the phase board.

### When to start

Trigger the review when one of these is true:

- All workstream items are marked complete on the phase board.
- The user signals the build is done ("I think we're ready to review," "feels finished").
- A workstream is blocked (waiting on input, external dependency) — review what's done so far.

### Generating the walkthrough

Pin the walkthrough to the phase thesis, then look at what the phase actually delivered. The core move is **triage**: every item is sorted by the kind of attention it needs, not by which workstream produced it. Three categories, ordered most-demanding to least:

1. **Open for your call · your judgment** — calls you made that another reasonable person might land differently. Magic numbers, naming compromises, scope cuts, V1 stubs. Lead with the call itself. Often the smallest section; zero is a valid count.
2. **Worth verifying · your hands** — behaviors that need a human at the keyboard: multi-step round-trips, stateful flows, interaction nuance, anything automated checks or a static screenshot couldn't catch. Each item: **what to check — where to look, what to do, what to expect.**
3. **Surfaces to glance · your eyes** — the surfaces the phase shipped; one look each confirms the thesis rendered. No steps, no expected-result spelling, no checkboxes.

Give items referenceable IDs by section — `O1, O2…`, `V1, V2…`, `G1, G2…` — so they can be named in chat ("let's revisit O2").

Don't pad. The structure exists to fight three habits: listing every state × surface permutation, spelling out what another item already exercises in passing, and dressing pure-visual nitpicks up as verification. A focused walkthrough beats a 30-item dump — past ~25 items, cut.

### Item format

Good "Worth verifying" item — actionable, names the expected result:

- [ ] **V1. Hero passes the screen-share test.** Open `index.html` at ~80% zoom, read the headline from across the room. Should remain legible.

Good "Surfaces to glance" item — one line, no steps:

- **G1.** Get-the-template CTA — links to the real repo URL, not `#`.

Bad (too vague to act on):

- [ ] Check the hero — make sure it looks good.

### Iterating

The walkthrough is a living document. As the user walks through:

- **Pass:** mark `[x]`. Move on.
- **Issue:** mark `[!]`, describe it inline, and route it (below). Decide whether to fix in this phase (note it, fix it, re-check) or punt.
- **Surface:** if walking one item reveals a new concern, add an item. Walkthroughs can grow during review.
- **Drift:** if a fix during review makes an existing item inaccurate, edit that item in the same change. Stale walkthrough text is worse than none.

### Logging decisions and routing follow-ups

The walkthrough's **"Decisions surfaced"** log captures calls made while checking — append as you walk, each entry annotated with its `→ home-doc.md`. Route everything else: punch list for small fixes, new phase on the roadmap for bigger work, `verification-checklist.md` for cross-phase checks, `open-questions.md` for unresolved questions.

### Completion

Review is complete when every item is `[x]`, fixed and re-checked, or explicitly accepted as good enough — and the "Decisions surfaced" log is ready for the phase-close sweep. Then move into the closing checklist.

## Closing a phase

When the phase thesis is delivered. **A phase close ends the chat session** — do not open the next phase in the same conversation. Context gets heavy, decisions blur, and review discipline weakens when build energy carries forward. The next phase opens in a fresh chat, started by the handoff message you write in step 12.

1. **Show the closing checklist to the user before starting.** Phase close is a high-leverage moment — confirm the list before editing docs.
2. **Sweep the walkthrough's "Decisions surfaced" log, then the phase board's Decisions log.** Each walkthrough entry carries a `→ home-doc.md` annotation — propagate it there. Then check the board's own Decisions log: anything load-bearing belongs in `decisions.md`, a feature doc, or a strategy doc — not just the board (it's about to be archived). The walkthrough can't archive until every entry has landed.
3. **Update affected feature docs** in `docs/features/`. Add new ones if the phase shipped a new feature.
4. **Update affected implementation docs** in `docs/implementation/`.
5. **Update `docs/strategy/open-questions.md`** — mark resolved, add new, update parked.
6. **Update `docs/decisions.md`** — log non-obvious decisions with dates and reasoning.
7. **Update `docs/ROADMAP.md`** — move phase to Closed, refresh upcoming list.
8. **Update `CLAUDE.md`** — Current Phase points at the next phase (or "between phases"), Strategic Context updated if anything fundamental shifted.
9. **Archive the phase board and its walkthrough** — move `docs/phases/<phase-name>.md` and `docs/phases/<phase-name>-walkthrough.md` → `docs/archive/phases/`. Set both frontmatter statuses to `archived`.
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
