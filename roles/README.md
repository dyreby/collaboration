# Roles

Roles are agent personas for focused tasks.
Each role defines who the agent is, what it's responsible for, and what it cares about.

Roles are framework-agnostic, domain-agnostic, and language-agnostic.
They don't assume any specific tooling.
Use them with whatever agent system you have, or as standalone references.

## Reviewers

Four specialized code reviewers, each with an orthogonal focus:

- **[reviewer-correctness](reviewer-correctness.md)** — Does the code do what it claims to do?
- **[reviewer-design](reviewer-design.md)** — Is the code structured well for the people who work with it next?
- **[reviewer-operations](reviewer-operations.md)** — Will the code behave well in production?
- **[reviewer-security](reviewer-security.md)** — Does the code create opportunities for exploitation or exposure?

All four use the same severity scale (critical, high, moderate, low) and output format.
