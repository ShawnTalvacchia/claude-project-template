---
status: active
last-reviewed: YYYY-MM-DD
review-trigger: "Update as items are walked; edit as scope shifts"
---

# [Phase Name] — Walkthrough

Verification for the [Phase Name] phase. Pinned to the phase thesis: **[restate the thesis as the one question this walkthrough answers]**

**Concise by design.** Not an exhaustive per-task checklist. Automated checks and visual sanity passes already ran during the build. Surface only what's worth a human's judgment, what risks regression, and what confirms the thesis landed. A walkthrough past ~25 items has almost certainly drifted into listing permutations — cut it.

**Who walks this:** [you, later · a collaborator · whoever reviews]. The "Open for your call" section assumes the walker can overrule the author.

**How to use:**

1. [How to run or open the thing — dev server, build command, file to open, login.]
2. [How to move between the states this walkthrough references — accounts, routes, data fixtures, personas.]
3. Walk top-to-bottom. Categories are ordered by the kind of attention each needs: your judgment → your hands → your eyes.

**Status legend:** `[ ]` not walked · `[x]` walked, fine · `[!]` walked, issue — note it inline and route it (see bottom).

<!-- Optional one-line context block: seed data, dates that matter, fixtures. Drop if not needed. -->

---

## Open for your call · your judgment

Calls the author made that another reasonable person might land differently — direction, not bugs. These are the decisions made during the build instead of stopping to ask — surfaced here so the reviewer can ratify or redirect. Lead with the call itself, so the reader knows what's being asked without reading the rest. Point them at the quickest way to see it in context. If there are none, say so in one line.

IDs: **O1, O2, …** (use them in chat: "let's revisit O2").

- [ ] **O1. [The call, in one line.]** Why it could go another way. ([Where to see it.])

---

## Worth verifying · your hands

Behaviors that need a human at the keyboard — multi-step round-trips, stateful flows, interaction nuance, anything automated checks or a static screenshot couldn't catch. Each item: **what to check — where to look, what to do, what to expect.**

IDs: **V1, V2, …**

- [ ] **V1. [Behavior to verify.]** [Where to look, what to do, what to expect.]

---

## Surfaces to glance · your eyes

The phase shipped these surfaces; confirming they render is the thesis check. One look each — no steps, no expected-result spelling, no checkboxes. Flag anything that reads off.

IDs: **G1, G2, …**

- **G1.** [Where] — [one line: what should be there.]

---

## Decisions surfaced during the walkthrough

A running **log** (not a checklist) — append as you walk, don't wait for the end. Each entry carries a `→ target-doc.md` annotation naming where it needs to land. At phase close, propagate each one to its home doc; the entries stay here as the historical record.

Format:

```
- **[Decision in one line.]** [Optional context.] → `features/foo.md`
- **[Implementation-only change.]** [What/why.] → no doc update needed
```

Route anything else that surfaced (the `[!]` items above included): small fix → `planning/punch-list.md` · bigger work → new phase on `ROADMAP.md` · cross-phase check → `planning/verification-checklist.md` · unresolved → `planning/open-questions.md`.

<!--
Authoring notes — read before writing this walkthrough.

WHAT GOES WHERE
  Open for your call — a call with a defensible alternative. If you'd shrug at
    someone changing it, it doesn't belong here. Often the smallest section;
    "no open calls — everything landed per spec" is a fine entry.
  Worth verifying — needs hands on the keyboard. NOT things that work-or-don't
    at a glance (those glance).
  Surfaces to glance — renders-correctly thesis checks. If the reader needs a
    paragraph to know what to look for, it's a "Worth verifying" item instead.

ANTI-PATTERNS (the structure exists to fight these)
  1. Listing every state x surface permutation. If verifying X in one state
     implies it works in the others (same code path), list it once.
  2. Spelling out what another item already exercises in passing. Trust the reader.
  3. Pure-visual nitpicks dressed as verification. Either it's fine (don't list
     it) or it's broken (fix it — don't ask the reader to flag it).

DRIFT RULE
  A code change that makes an item inaccurate gets the item edited in the SAME
  change. Stale walkthrough text is worse than none — it sends the reader looking
  for behavior that's gone. Same for the Decisions log: if a logged decision is
  superseded, EDIT the entry, don't append a contradicting one.

LENGTH (rough): Open 0-6 · Verify 4-10 · Glance 4-10. Past ~25 total = cut.
-->
