# Working Document

Any work on a branch should have a `WORKING.md` at the repo root. It's a living document that carries context forward so any session — human or agent — can orient without archaeology.

## When to create one

Default to yes when creating a branch. Skip it only when the work is trivially small — a one-line fix, a typo. If there's any design intent, any decisions to track, or any chance of more than one session, create it.

## What goes in it

- **Goal** — what we're trying to be true when the work is done.
- **Invariants** — what we believe must hold. Articulate these before building. When something breaks, trace it back here.
- **Decisions** — what's been decided and why. Lock decisions so they don't get re-litigated.
- **Progress** — what's happened, what's next. A handoff surface between sessions.
- **Open questions** — what's unresolved. Better to name uncertainty than to build on assumptions.

Not everything needs every section. Start with what's useful and add structure as the work demands it.

## Lifecycle

`WORKING.md` is committed to the branch. It's shared context — anyone working on the branch can read it and update it. Keep it current as decisions are made and work progresses.

Remove it before merging to main. The working document serves the branch, not the project. Durable context (docs, comments, changelog entries) should be moved to its permanent home before the branch lands.

## Not scratch files

`WORKING.md` is not a scratch pad. It's a deliberate artifact that captures what matters about the work in progress. If something isn't worth committing to the branch, it probably isn't worth writing down.
