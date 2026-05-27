---
status: active
last-reviewed: YYYY-MM-DD
review-trigger: phase close
---

# [Phase Name] — opened YYYY-MM-DD

## Thesis

[One paragraph. The structural change this phase delivers. Not a feature list — the *shape* the project takes on by the end. Example: "After this phase, X is a first-class concept in the data model and surfaces consistently across A, B, and C."]

## Opening Checklist

Before starting work:

- [ ] Read referenced strategy docs:
  - `docs/strategy/product-vision.md`
  - `docs/strategy/user-archetypes.md`
  - [Others specific to this phase]
- [ ] Review `docs/strategy/open-questions.md` for blocking questions
- [ ] Skim affected feature docs:
  - [List]
- [ ] Confirm thesis with user before opening workstreams

## Workstreams

### A · [Workstream name]

[Scope. What's in, what's not.]

- [ ] Task 1
- [ ] Task 2

### B · [Workstream name]

[...]

## Review

After workstreams land, Claude generates a walkthrough — a streamlined checklist of what to verify, with context on where to look, what to do, and what to expect. You go through it manually, slow and deliberate. The checklist revises as items get checked off; a decisions log at the end captures anything new that surfaced (unless already documented elsewhere). This is the longest step; it's where most of the phase's intelligence lands.

For designers especially: step out of the build conversation. Evaluate, compare, tinker. Open Figma if that's where you think.

### Verification walkthrough

- [ ] [Item to check] — [Where to look, what to do, what to expect]
- [ ] [...]

### Decisions during review

[Decisions made while walking through the checklist — log here unless already documented elsewhere (e.g., `decisions.md`, feature docs).]

### Surfaced elsewhere

[Items to route: punch list (small fix), new phase entry on roadmap (bigger work), `verification-checklist.md` (cross-phase check), `open-questions.md` (still unresolved).]

## Decisions log

Capture non-obvious calls as they happen. Format:

```
### YYYY-MM-DD · Short title
What: [decision]
Why: [reasoning, alternatives considered]
```

[At phase close, load-bearing entries move to `docs/decisions.md`.]

## Closing Checklist

Before archiving:

- [ ] Walked the user through this checklist before editing docs
- [ ] Decisions log items moved to appropriate homes (`decisions.md`, feature docs, strategy docs)
- [ ] Affected feature docs in `docs/features/` updated
- [ ] Affected implementation docs in `docs/implementation/` updated
- [ ] `docs/strategy/open-questions.md` updated (resolved / parked / new)
- [ ] `docs/decisions.md` updated with non-obvious calls
- [ ] `docs/ROADMAP.md` updated (phase moved to Closed; upcoming refreshed)
- [ ] `CLAUDE.md` updated (Current Phase + Strategic Context if changed)
- [ ] This phase board moved to `docs/archive/phases/` and frontmatter `status: archived`
- [ ] Structural audit: read CLAUDE.md + ROADMAP + strategy docs end-to-end, trim staleness
- [ ] Evaluated next candidate (reviewed ROADMAP + open-questions; discussed with user if not obvious)
- [ ] Wrote handoff message for the next chat (next phase name + thesis, docs to read, open questions, starting workstreams)
- [ ] **Ended the session.** The next phase opens in a new chat — do NOT continue here.
