# Levels of Alignment

[The gap](the-gap.md) explains why alignment is hard.
This model describes alignment as occurring at different levels of abstraction.
Understanding that structure helps you focus where alignment actually matters, and let go where it doesn't.

## Levels

A collaborative effort can be understood at different levels of abstraction — from the purpose of the project down to the details of implementation.
At every level there's a *what* (the intent) and a *how* (the approach).
Each *how* contains its own *what* and *how* at the next level of detail, all the way down to tabs versus spaces.

For example, a team agrees on what to build.
The approach they choose is the *how* that becomes the *what* for the people designing it.
The design they create is the *how* that becomes the *what* for the people implementing it.

Not everyone needs to be involved at every level.
A project's purpose concerns everyone involved.
A subsystem's design concerns the people working on and around it.
An implementation detail concerns whoever is writing the code or will maintain it.

Fewer people are involved at each successive level, until often the work is yours alone.

## Encapsulation

When the *what* at a level is genuinely shared, the *how* below it can proceed independently.
You don't need to understand every decision below to trust the work at a given level, and the people above don't need to understand yours.

People engage where they care about the *what*.
Once they're satisfied the shared understanding at that level is sufficient, they can trust the people at the next level down to own the *how*.
That's encapsulation — and it lets everyone focus on their work instead of the coordination around it.

## Locating the level

When something shifts — a change, a disagreement, a pattern of rework — the most important question is: which level does it affect?

A change to *how* something is implemented is different from a change to *what* a component does, which is different from a change to *what* the project is for.
The people involved, the response, and the ripple effects all depend on the level.

Friction is often the signal.
A persistent argument about implementation may mean the *what* behind it isn't shared.
A design that keeps getting reworked may point to an unresolved question in the vision.

The response is not to escalate but to locate.
Step back to the level where alignment broke down and rebuild from there.
Once the *what* is shared again, the *how* tends to resolve on its own.

## Sufficient alignment

Alignment can't be perfect, but it doesn't need to be.
It just needs to be sufficient.

Over-alignment creates noise.
A junior developer doesn't need the CEO's full strategic context, and couldn't use it.
The right level for them is: this feature matters, build it well.

Under-alignment creates gaps.
A developer who doesn't know *why* a feature matters will make poor tradeoffs when edge cases appear.

The right level of alignment is discovered, not prescribed, and it shifts as the work evolves.
When you find it, the work becomes light.
