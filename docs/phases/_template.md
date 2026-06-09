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
- [ ] Review `docs/planning/open-questions.md` for blocking questions
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

After workstreams land, Claude generates a **walkthrough** as its own doc — `docs/phases/<phase-name>-walkthrough.md`, from `_walkthrough-template.md`. It's a streamlined, triaged checklist of what to verify, sorted by the kind of attention each item needs: **your judgment** (calls worth a second opinion), **your hands** (behaviors to drive), **your eyes** (surfaces to glance). You go through it manually, slow and deliberate. It revises as items get checked; a decisions log at the bottom captures anything that surfaces, each entry routed to its home doc. This is the longest step; it's where most of the phase's intelligence lands.

For designers especially: step out of the build conversation. Evaluate, compare, tinker. Open Figma if that's where you think.

See `docs/CONTRIBUTING.md` → "Running a review" for how to generate and walk it. The walkthrough doc and this board archive together at phase close.

## Decisions log

Capture non-obvious calls as they happen. Format:

```
### YYYY-MM-DD · Short title
What: [decision]
Why: [reasoning, alternatives considered]
```

[At phase close, feature-specific entries move to their feature doc; cross-cutting ones to `docs/decisions.md`. The archived board itself stays as the dated record.]

## Closing Checklist

Before archiving:

- [ ] Walked the user through this checklist before editing docs
- [ ] Walkthrough's "Decisions surfaced" log swept — each entry propagated to its `→` home doc
- [ ] Decisions log items moved to appropriate homes (`decisions.md`, feature docs, strategy docs)
- [ ] Affected feature docs in `docs/features/` updated
- [ ] Affected implementation docs in `docs/implementation/` updated
- [ ] `docs/planning/open-questions.md` updated (resolved / parked / new)
- [ ] `docs/decisions.md` updated with non-obvious cross-cutting calls (feature-specific ones went to feature docs)
- [ ] `docs/ROADMAP.md` updated (phase moved to Closed; upcoming refreshed)
- [ ] `CLAUDE.md` updated (Current Phase + Strategic Context if changed)
- [ ] This phase board **and its walkthrough** moved to `docs/archive/phases/`, both frontmatter `status: archived`
- [ ] Structural audit: read CLAUDE.md + ROADMAP + strategy docs end-to-end, trim staleness
- [ ] Evaluated next candidate (reviewed ROADMAP + open-questions; discussed with user if not obvious)
- [ ] Wrote handoff message for the next chat (next phase name + thesis, docs to read, open questions, starting workstreams)
- [ ] **Ended the session.** The next phase opens in a new chat — do NOT continue here.
