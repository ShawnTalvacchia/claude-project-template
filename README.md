# Claude Project Template

A docs-driven workflow template for projects built collaboratively with Claude. Skeletons for a strategy → roadmap → phase board → side tasks system that keeps Claude oriented across long projects without bloating context.

## Quick start

1. Copy this folder to a new project directory and rename it.
2. Open the project in Claude (Code, claude.ai, or wherever you work).
3. Paste the contents of `setup-prompt.md` into Claude.
4. Answer Claude's inquiry questions. Claude will fill in the stub docs and propose your first phase.

Budget 30–90 minutes for inquiry + setup. That feels like overhead. It isn't — it's the part of the project where decisions are cheapest to change and most expensive to skip.

## What's inside

```
.
├── CLAUDE.md                          ← Project rules, loaded into every Claude session
├── setup-prompt.md                    ← Run this once, on day one
└── docs/
    ├── ROADMAP.md                     ← Phase overview, current state
    ├── CONTRIBUTING.md                ← Workflow rules — the canonical "how we work" doc
    ├── decisions.md                   ← Cross-cutting decisions with no feature/strategy home
    ├── strategy/                      ← What you're building and why (settled)
    │   ├── product-vision.md
    │   └── user-archetypes.md
    ├── planning/                      ← Running lists that feed scheduling (pending)
    │   ├── open-questions.md          ← Unresolved questions — review before each phase
    │   ├── future-considerations.md   ← Known directions waiting for a trigger
    │   ├── punch-list.md              ← Tiny isolated fixes
    │   └── verification-checklist.md  ← Things to verify before milestones
    ├── phases/                        ← Active work: boards + walkthroughs (+ molds)
    │   ├── _template.md               ← Copy this when opening a new phase
    │   └── _walkthrough-template.md   ← Copy this when a phase reaches review
    ├── features/                      ← What's built — one doc per feature
    │   └── _template.md
    ├── implementation/                ← How it's built — patterns + conventions
    │   └── _template.md
    └── archive/phases/                ← Closed phase boards live here
```

## The philosophy

- **Docs-first.** Decide before you build. Strategy → roadmap → phase board → code. Each step makes the next one cheaper.
- **Phased work.** A phase is a focused chunk of work with a thesis (the structural change it delivers). It has an opening checklist, workstreams, a decisions log, and a closing checklist. You only ever have one or two phases open at a time.
- **Three sizes of work.** Phases (multi-task design work) → side tasks (~30min–few-hour focused PRs) → punch list (≤30min isolated fixes). Match the work to the right size.
- **Thin `CLAUDE.md`.** Project rules + pointers, not history. Closed phases archive out. Decisions move to `decisions.md`. The file Claude loads every session stays small.
- **Trust the system, not the conversation.** Anything load-bearing goes in a doc, not chat. The next conversation reads docs cold — they're the handoff.

## Iterating on the template

If you discover workflow tweaks that work in practice, port them back here. The template is meant to evolve.
