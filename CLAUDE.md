# [PROJECT NAME] — Project Instructions

Read this before every session. These rules override defaults.

## Stack

[FILLED BY SETUP. List: language/framework, key libraries, deployment, dev server command.]

## Workflow rules

See `docs/CONTRIBUTING.md` for full details.

1. **Work from the current phase board** in `docs/phases/`. Check it before starting.
2. **Read referenced docs** before starting a task. Update them if anything changed.
3. **Doc frontmatter:** Every doc has `status`, `last-reviewed`, `review-trigger`. Update `last-reviewed` when you touch a doc.
4. **No feature sprawl.** If it's not on the phase board, surface it — don't build it without discussion. (Side task or punch list might be the right home; see CONTRIBUTING.)
5. **Phase close = doc review.** Update feature docs, decisions log, ROADMAP, and this file. Archive the phase board.
6. **One phase = one chat.** Closing a phase ends the session. The next phase opens in a new chat, started by a handoff message the user pastes in. Don't continue in the same conversation.
7. **Decide, don't stall.** While building, make reasonable design and implementation calls and keep moving — don't stop at every fork to ask. Raise true blockers and anything that shifts scope or strategy, but surface ordinary judgment calls in the walkthrough's "Open for your call" rather than asking permission mid-build. Deciding fast and explaining the choice beats pausing for approval.
8. **Push back; don't just comply.** When there's a better approach than what's asked, say so and make the case — briefly. Lead with a clear recommendation, not a menu; surface alternatives only when they're genuinely worth weighing, and offer to expand rather than front-loading detail. Challenge on merit, not reflex — the goal is a better outcome, not the appearance of rigor.
9. **System work is its own mode.** Meta-work on the docs/workflow themselves — rewriting rules, restructuring a tracker, editing this file or the ROADMAP's structure — isn't a phase or a side task. It's the one mode allowed to touch the governance docs, done with the user between phases as its own commit. See CONTRIBUTING → "System work."

## Key docs

| Doc | What it covers |
|-----|---------------|
| `docs/ROADMAP.md` | Phase overview, current state, upcoming work |
| `docs/CONTRIBUTING.md` | Workflow rules, the four work modes, phase lifecycle, the planning trackers |
| `docs/decisions.md` | Cross-cutting project decisions (workflow, conventions, structure) — feature decisions live in their feature doc |
| `docs/strategy/product-vision.md` | Product strategy, principles, what's in/out of scope |
| `docs/strategy/user-archetypes.md` | Behavioral profiles of who this is for |
| `docs/planning/open-questions.md` | Unresolved questions — review before each phase |
| `docs/planning/future-considerations.md` | Known-direction items waiting for a trigger |
| `docs/planning/punch-list.md` | Small isolated fixes (P1, P2, …) |
| `docs/planning/verification-checklist.md` | Cross-phase checks to run before milestones |
| `docs/features/` | Specs for features you've built |
| `docs/implementation/` | Patterns + conventions |

## Current phase

[FILLED BY SETUP. Update on every phase open/close. Pointer to `docs/phases/<phase-name>.md` + 1–2 line thesis.]

## Strategic context

[FILLED BY SETUP. 5–10 lines summarizing the decisions that shape day-to-day work. Not the elevator pitch — the calls that affect what gets built and how.]
