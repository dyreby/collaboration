# Principles

These are the beliefs that inform how I work and collaborate.
They apply across domains, languages, and tools.

## Understand before acting

Know what you're working with before you change it.
Read the context (docs, code, conversation history) and understand the intent behind what's already there.
Align at the right level: enough shared understanding to move forward, not so much that it becomes overhead.

## Go upstream when stuck

When friction persists, the problem is usually one level above where you're looking.
If you can't agree on *how*, check whether you actually agree on *what*.
Step back to where alignment exists and work down from there.

## Separate concerns

One thing should have one job.
Catch tangled responsibilities during design, not in review.
This applies to code, to processes, and to conversations. Keep things focused so they're easier to reason about and change.

Related principles:

- Single Responsibility Principle (SRP)
- Separation of Concerns
- Composition over Inheritance
- Dependency Inversion
- Law of Demeter
- Functional Core, Imperative Shell

## Design for correctness

Make the wrong thing hard to do, not just the right thing easy.
Use types, structure, and constraints to prevent invalid states from existing rather than catching them after the fact.

Related principles:

- Make Illegal States Unrepresentable
- Parse, Don't Validate
- Explicit over Implicit
- Open/Closed Principle

## Design for failure

Assume things will go wrong. Build so that when they do, the blast radius is small and recovery is possible.
Inputs will be bad, dependencies will be slow, access will be misused. Design for it.

Related principles:

- Idempotency
- Back Pressure
- Defense in Depth
- Principle of Least Privilege

## Start with the least

Start with the smallest thing that could work.
Don't over-engineer the solution, the process, or the correction.
Act incrementally. Show work early, course correct, and refine when friction demands it rather than in advance.

Related principles:

- YAGNI (You Aren't Gonna Need It)
- KISS (Keep It Simple)
- Rule of Three

## Verify before sharing

Check your own work before putting it in front of someone else.
Run the tests, read the diff, re-read what you wrote.
When you're uncertain, say so. Surfacing doubt early is cheaper than fixing confident mistakes later.
