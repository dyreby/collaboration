# Why is there a model in the middle?

I've noticed a pattern that repeats across software: a canonical model in the middle that producers and consumers communicate through.
This shared abstraction takes the form of schemas, desired states, main branches.
Even the "average user" is a model of the typical person that interfaces and frontends are designed around.
Much of our field's intellectual energy goes into making that model better.
Very little of it goes into asking whether the model should be there.

## The fiction

A canonical model is a fiction we agree to share, so that two sides of a system can be reconciled without knowing each other directly.
That fiction is necessarily lossy because it averages over the input it accepts, the people it serves, and the history it summarizes.
The cost of the lossiness is paid forever, in friction that accumulates at every layer above.

This friction has a name worth using: *made-up problems*.
These problems are not intrinsic to the work.
They emerge from the gap between the model and the reality it claims to represent.
Every layer above the model pays for that gap, in attention spent on problems no one set out to solve.

The fiction recurs at smaller scales.
A database picks a schema, calls it the model, makes everyone read and write through it.
Version control picks a main branch, calls it the canonical history, treats every other history as a deviation.
Software picks an average user, calls them the model, and ships something shaped to that average.
Configuration management picks a desired state, calls it the truth, treats reality as drift.
It's the same move at every scale — replace what actually happened with a model, and call the model the truth.

## Locating the question

The question we tend to ask, without using this exact phrasing, is *what is the right model in the middle?*
Better schemas, better personas, better averages over people we do not get to know, better training weights for LLMs to serve those people.
Collectively, we're pretty good at our job: each iteration is genuinely better at the thing it is optimizing.

But I think that this question is one level too low.
Optimizing the answer reinforces the assumption that the question itself is the right one to ask.

Occam's razor isn't a new idea.
A good developer looks for unnecessary abstractions to remove because we've learned that simpler models are easier to understand, maintain, and extend.
On Stack Overflow this pattern has a name: the *XY problem*.
The asker knows they want to do X and assumes Y is the way to get there, so they ask how to do Y, often in a way that doesn't quite make sense.
A back-and-forth starts, with varying degrees of patience from the answerers, until the asker reveals the X they were after.
The answer turns out to be: don't do Y, here's how to do X directly.
The asker's assumption was itself a model in the middle, blocking the help they needed.
The XY problem is familiar enough that the lesson we usually take from it is "that person should have known to ask the right question."
But the same pattern is harder to see at the scale of our entire field, especially when refining Y is what we get paid for.

The question one level above that I want to ask:
*Why is there a model in the middle at all?*

## What a model is

The hidden assumption underneath the model in the middle is that two sides of a system can only be reconciled through a shared abstraction.
That assumption is not load-bearing.
The two sides can also be reconciled through shared access to the events along the way, with each writing to, or reading from, that record.
The record of events is observable; the model is constructed.
Treating the constructed thing as primary, and the record as derived, mistakes which one produced the other.

Models have a useful place in software, but not as the source of truth (which makes sense, since they're all wrong).
Where they earn their keep is as a *projection* over events, computed by whoever needs it, when they need it, and in the shape they need it in.
The shape that serves the writer is rarely the shape that serves the reader; each is free to project their own.
Demoting models from primary to derived does not remove them.
It returns them to the people and systems doing the projecting, where they belong.

## Permanence

As humans, we build internal models of the world that are shaped by our learned experiences and are generally very useful.
The more stable the model, the more comfortable we feel applying it to the moment unfolding in front of us.
But it's also easy to forget, especially for models that have been proven useful many times over, that all models are wrong.
The most useful ones can become invisible.

The model in the middle is one of those.
It has been the unexamined floor of software for decades, and we're fluent in it.
"What is the right schema" feels like *the* engineering question.
Asking whether the schema needs to be there at all sounds either obvious or unhinged, depending on who's listening.

What feels permanent often isn't.
New York City was once seriously worried about being buried in horse manure — a real problem, eating real money and time and attention.
The fix didn't come from optimizing within the constraint.
Cars arrived from outside the constraint entirely, and the question dissolved.

## What changes

If we treat the timeline of authored events as primary, the things we currently call "the model" become projections: views computed from events, owned by their consumer, shaped to the moment of use.
There's no single canonical schema; there are projections per consumer.
There's no main branch fighting parallel work; there's the actual graph of what people did, with views computed for whoever needs one.
There's no average user shaping the software; there's a record of what each person authored, projected into the shape that fits them.

Existing canonical systems (databases, git, conversations on GitHub, whatever we depend on) become projections of the timeline.
Integration stops being architectural and becomes a shell concern.
The made-up problems that flowed downstream from the model in the middle stop being intrinsic to the work.

## The work

Answers shaped by this question already exist, scattered under other names: event sourcing, CQRS, content-addressed builds, log-structured anything.
Each is a partial answer; what they share hasn't yet been named.

My work moving forward is to model this substrate over which events are observed, because I believe we can encode a core model of events unfolding in time that will be generally useful across all software domains.

My motivation for this work is simple.
I want to live in a world with fewer made-up problems. A world where good people can spend their attention on real ones: treating diseases, ending food insecurity, mitigating climate change. We developers can build the tools that make that possible, but it's a ladder, and the bottom rung is better tools for ourselves.
