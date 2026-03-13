# Git Practices

## Commit hygiene

Read the diff before committing.
`git diff --staged` is the last checkpoint before the commit exists.
Catch stale comments, leftover imports, debug prints, or unintended changes here.

Commit messages lead with what changed, not how.
The diff shows the how.
The message tells a reader scanning the log what happened and why it matters.

Separate functional changes from release commits.
A release commit (version bump, changelog, tag) should contain only release mechanics.
The actual changes it releases should already be in the history as their own commits.
Combining both makes it impossible to revert the change without reverting the release, and hides the functional change behind a version bump message.

## Linear commit histories

Every commit on main should be a meaningful, self-contained unit of work.
The history reads like a changelog — each entry tells you what changed and why.

Squash merge is the default.
A PR's exploration, fixups, and review responses collapse into one commit that represents the outcome.
The branch preserves the journey if anyone needs it; main preserves the result.

Rebase to stay current with the base branch.
Merge commits add noise and make the history harder to bisect.

## Branch and review workflow

Start branches from the latest base.
Pull before branching.
Stale starts cause avoidable conflicts and make the diff harder to read.

Close the loop on feedback.
When pushing commits that address review discussion, comment with what you took away, what you changed, and link the commit.
Reviewers shouldn't have to re-read diffs to verify alignment.

Don't push mid-conversation.
When iterating on design, align first, push when aligned.
Pushing while the conversation is still active fragments the trail and creates noise.

Re-request review when the work is ready for another look, not while still iterating.
The review surface should reflect aligned work, not a mid-discussion snapshot.

## GitHub

If a reviewer approves, don't re-request their review after making changes — they've said they're done.
If a reviewer requests changes, they want to see the next iteration — re-request their review when it's ready.
