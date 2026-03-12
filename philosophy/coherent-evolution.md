# Coherent Evolution

The gap explains why alignment is hard.
This is a model for thinking about what alignment looks like when it's working.
> a model, for thinking about, what it looks like, when it's working. That's a bit convoluted. what's the simpler sentence to express the idea?

## Levels

Collaboration happens at levels of abstraction.
At every level there's a *what* (the intent) and a *how* (the approach).
Each *how* becomes the *what* for the level below it.
> Is this immediately clear? I feel like the framing of "each how contains its own what and how" was more obvious to me

> This paragrpah is jumping into a different concept, about who cares at which level. but it didn't introduce it.
A project's purpose concerns everyone involved.
A subsystem's design concerns the people working on and around it.
An implementation detail concerns whoever is writing the code.
> writing the code or is expected to work with it

Fewer people are involved at each successive level, until the work is yours alone.

## Encapsulation

When the *what* at a level is genuinely shared, the *how* below it can proceed independently.
You don't need to understand every implementation choice to trust a subsystem, and you don't need to understand every subsystem to trust the project is heading in the right direction.

This is how collaboration scales without becoming a bottleneck.
People engage where they care about the *what*.
Once they're satisfied the shared understanding is sufficient, they release the *how* to the people working at the next level down.
> we shoudl soften a bit. "They can choose to release..."
Those people can work without checking back constantly.

That trust only holds when the *what* is genuinely shared. When it isn't, encapsulation breaks.

## Sufficient alignment

Alignment doesn't need to be perfect, it just needs to be sufficient for the task at hand.

Over-alignment creates noise.
A junior developer doesn't need the CEO's full strategic context, and couldn't use it.
The right level for them is: this feature matters, build it well.

Under-alignment creates gaps.
A developer who doesn't know *why* a feature matters will make poor tradeoffs when edge cases appear.

The right level of alignment is discovered, not prescribed.
Step back to where agreement is obvious, then step down until you find where the work lives.
That's where collaboration becomes light.
> I want to say the work become light here. so the sentence above will need to be tweaked to avoid "work"

## Change has a level

When something changes, the most important question is: which level does it affect?

A change to *how* something is implemented is different from a change to *what* a component does, which is different from a change to *what* the project is for.
The people involved, the response, and the ripple effects all depend on the level.

Recognizing the level of a change lets you respond proportionally instead of treating every shift as equally significant.

## Friction signals upstream

Friction at one level often signals misalignment at the level above.

A persistent argument about implementation may mean the *what* behind it isn't shared.
A design that keeps getting reworked may point to an unresolved question in the vision.

The response is not to escalate but to locate.
Step back to the level where alignment broke down and rebuild from there.
Once the *what* is shared again, the *how* tends to resolve on its own.

## Artifacts

Two kinds of artifacts support alignment across levels.

**Artifacts of clarity** capture where alignment stands now.
A charter, a design document, the code itself — whatever makes the *what* at a given level legible.
The form doesn't matter. The test is whether someone joining at that level can understand the intent and contribute.

**Artifacts of change** capture how alignment got there.
Issues, pull requests, commit messages, conversation threads — the reasoning behind decisions.
This matters because the context behind a decision fades.
When artifacts of change are working, someone can trace a decision back to the tradeoffs that were weighed.

Not every decision needs a trail. The overhead should match the stakes.

## Relationship to the gap

The gap tells you that misalignment is structural and iteration is necessary.
Coherent evolution tells you where to iterate.

When correction at one level isn't converging, it's usually because the real divergence is one level up.
Recognizing that pattern lets you focus on the right problem.
