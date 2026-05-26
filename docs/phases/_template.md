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

After workstreams land, produce a walkthrough — a checklist of what to verify, with context on where to look, what to do, and what to expect. Then slow down and walk through it. This is the longest step; it's where most of the phase's intelligence lands.

For designers especially: step out of the build conversation. Evaluate, compare, tinker. Open Figma if that's where you think.

### Verification walkthrough

- [ ] [Item to check] — [Where to look, what to do, what to expect]
- [ ] [...]

### Surfaced during review

[Questions, follow-up tasks, ideas. Each item gets routed: into the decisions log if it's a decision, the punch list if it's small, a new phase entry on the roadmap if it's bigger, `verification-checklist.md` if it's a cross-phase check, or `open-questions.md` if it's still unresolved.]

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
