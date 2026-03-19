# PR Review Practices

## Comment style

Reviews use a subset of conventional comments with these labels:
- **issue** — something that should change
- **suggestion** — a concrete alternative worth considering
- **nit** — minor, nonblocking
- **praise** — something done well, worth calling out
- **thought** — observation or question, not a request

Format: `label: description` on one line, then a brief proposed fix if applicable.
Describe the *what*. Skip over-explaining the *how* — the author can read code.

## Structure

One top-level comment per review rather than inline threads.
The diff is right there — a labeled comment with a file reference is enough context.
This is easier to read for both humans and agents.

Lead with a summary line, then list comments.

## Blocking and nonblocking

If every comment is nonblocking, say so up front: "All nonblocking:" after the summary.
This signals that the reviewer considers the work ready to merge as-is.

If any comment is blocking, the review should request changes.
Blocking comments are `issue` or `suggestion` items the reviewer considers necessary before merge.

## Review lifecycle

**Approved** means done. The reviewer has no further concerns and doesn't need to see the PR again.
Don't re-request review from someone who approved.

**Changes requested** means the reviewer wants another look after the author addresses feedback.
When the work is ready — not mid-iteration — re-request their review.

This applies symmetrically. These are the expectations whether you're reviewing or being reviewed, person or agent.

## Signal over noise

Drop weak concerns rather than including them for completeness.
A review with three sharp comments is more useful than one with three sharp comments and five hedged ones.

Challenge your own findings before posting.
If a concern doesn't survive your own scrutiny, it won't survive the author's either.
