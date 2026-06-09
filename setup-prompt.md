# Project setup — inquiry prompt

You are starting a new project with this template. **Do not write code yet.** Your first job is inquiry — interview the user about what they're building, why, and for whom. Then fill in the stub documentation and propose the first phase of work.

## Why this matters

The template ships with empty strategy docs, an empty roadmap, and an empty CLAUDE.md. They stay empty until you and the user finish the inquiry. The inquiry is the only way you build a real understanding of the project — the questions you ask now shape every conversation you have on this project later.

Resist the urge to skip ahead. If the user pushes to start building before the inquiry is done, name the tradeoff and let them choose, but recommend completing the inquiry first.

## Your mission

1. Read every file in this template so you know the structure you're filling in.
2. Run the inquiry below — one round at a time, conversationally.
3. Fill the stub docs with what you learn.
4. Propose the first phase of work, written as a phase board in `docs/phases/`.
5. Update `CLAUDE.md` so future sessions load with full context.
6. Hand off — tell the user the inquiry is complete and the first phase is ready.

## Inquiry — six rounds

Run these one at a time. After each round, capture what you learned in the relevant doc, then move to the next round. Don't batch all six questions in one message; the value is in the back-and-forth.

### Round 1 — What is this?

Ask:
- In one paragraph, what are you building?
- Why now? What changed (in the world, in your life, in a market) that made this worth doing?
- What does the finished thing look like? (A prototype? A real product? A research artifact? A demo for investors?)

→ Capture in `docs/strategy/product-vision.md` (elevator pitch + why now + success criteria).

### Round 2 — Who is it for?

Ask:
- Who are the people you're building this for? Name 1–3 specific archetypes.
- For each: what are they doing today instead? Why doesn't that work?
- What's the moment in their day or week when they'd reach for this?

→ Capture in `docs/strategy/user-archetypes.md`. Behavioral profiles, not demographic profiles. "Anxious new owner who Googles every symptom" beats "25–34 urban professionals."

### Round 3 — Principles + boundaries

Ask:
- What are the 3–5 principles this product won't compromise on? (Examples: "community-first," "privacy by default," "no growth hacks.")
- What's explicitly OUT of scope? What might you build later but not now?
- What's the one thing that, if it broke, would make you walk away from the project?

→ Capture in `docs/strategy/product-vision.md` (principles + out-of-scope sections).

### Round 4 — Open questions

Ask:
- What are you still unsure about? What hasn't been decided?
- What would you need to learn or test to resolve each one?

→ Capture in `docs/planning/open-questions.md`. These are first-class artifacts — review them at the top of every phase.

### Round 5 — Stack + constraints

Ask:
- What are you building with? (Language, framework, tooling, deployment target.)
- Any constraints that shape decisions? (Solo developer? Time budget? Existing codebase? Specific deadline?)

→ Capture in `CLAUDE.md` (Stack section + Strategic Context).

### Round 6 — First phase

Now that strategy is captured, propose the first phase of work. The first phase is usually one of:
- **Foundations** — set up the scaffolding, pick conventions, make boring decisions early.
- **Riskiest assumption first** — build the thing that, if it doesn't work, kills the project.
- **Smallest demo-able slice** — the thinnest version of the experience end-to-end.

Propose 2–3 options. Let the user pick. Then write the phase board to `docs/phases/<phase-name>.md` using `docs/phases/_template.md`.

## After the inquiry

When all six rounds are done and the docs are filled:

1. Update `CLAUDE.md` — Current Phase section points at the new phase board; Strategic Context summarizes the key decisions in 5–10 lines.
2. Update `docs/ROADMAP.md` with current state + active phase + 2–4 upcoming phases.
3. Add entries to `docs/decisions.md` for any non-obvious decisions that came up during the inquiry.
4. Tell the user: inquiry complete, first phase ready to open, here's the link to the phase board.
5. Delete `setup-prompt.md` — it's done its job.

## Notes on style

- **Ask one question at a time.** Wait for the answer before moving on.
- **Push back gently** when something doesn't add up. The user is hiring you to be a real thinking partner for this hour, not a stenographer.
- **Quote the user back to themselves** in the docs. If they said "I want it to feel like calling a friend," put that line in `product-vision.md`. Their voice matters more than yours.
- **Mark uncertainty** as an open question. Don't paper over ambiguity by inventing detail.
- **Resist scope creep during inquiry.** When the user surfaces six features, capture three as "out of scope (for now)" and move on. The point is to ship something, not catalog everything.
