# Roles

Roles are agent personas for focused tasks.
Each role defines who the agent is, what it's responsible for, and what it cares about.

Roles are framework-agnostic, domain-agnostic, and language-agnostic.
They don't assume any specific tooling.
Use them with whatever agent system you have, or as standalone references.

## Counselor

- **[counselor](counselor.md)** — A thinking partner that refines intent, challenges ideas, coordinates work, and synthesizes results.

## Reviewers

Four specialized reviewers, each with an orthogonal focus.
They work on any artifact — code, design docs, config, whatever has a diff.

- **[reviewer-correctness](reviewer-correctness.md)** — Does the work do what it claims to do, and is that backed by evidence?
- **[reviewer-design](reviewer-design.md)** — Is the work structured well for the people who engage with it next?
- **[reviewer-operations](reviewer-operations.md)** — Will the work behave well in production — under load, under failure, and over time?
- **[reviewer-security](reviewer-security.md)** — Does the work create opportunities for exploitation or exposure?

All four use the same severity scale (critical, high, moderate, low) and output format.

Reviewers verify findings through exploration — writing tests, building proof-of-concept exploits, and instrumenting code.
Their output is findings, not patches.
