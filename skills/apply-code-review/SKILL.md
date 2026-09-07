---
name: apply-code-review
description: Implement the findings from a code review. Use when given a
  code-review output (directly or via a handoff file) and asked to apply,
  implement, action, or fix the findings. Defines the decision procedure
  for each finding — when to apply, when to decline with reason, when to
  defer. Do NOT use for running the review itself (use code-review) or for
  unrelated implementation work.
---

# Applying a Code Review

A finding states a problem and what "resolved" looks like, not a patch. You
own the implementation: make the smallest change that resolves it, and say
what you did.

For each finding in the review — regardless of severity — produce one of:

1. **Applied.** Made the change. Note the file and line.
2. **Declined with reason.** Evaluated and chose not to apply. State the
   specific reason. "Marked Consider" is not a reason. "Refactor not
   requested" is not a reason — the review IS the request. Valid reasons
   include: conflicts with in-flight work the reviewer couldn't see,
   resolving it would break a contract elsewhere in the codebase, you
   disagree with the reviewer's reasoning (say what you disagree with).
3. **Deferred with reason.** Change is correct but belongs in a separate
   commit. State why and where you tracked it.

## Findings about prose

When the finding is about a comment, docstring, or test name that no longer
matches the code, choose between the three outcomes above by this rule:
**delete rather than reword** whenever the sentence is not load-bearing.
Rewritten prose is new review surface, so a reword invites the next reviewer
to refine it again, while a deletion closes the finding permanently. Deleting
is **Applied**. Keeping a sentence whose remaining imprecision is harmless is
**Declined**, and "the prose this finding corrects should be removed or left
alone, not made more exact" is a complete reason for it.

## Severity meaning for the implementer

- **Must fix** — apply unless you can articulate why the reviewer is wrong.
- **Should fix** — apply unless it conflicts with something the reviewer
  couldn't see.
- **Consider** — judgment call. Evaluate the actual code and the change it
  would take, and decide. If that change is small and the reasoning sound,
  apply it.

## Output format

Group by outcome, not by severity:

## Applied
- <file:line> — <what changed>

## Declined
- <file:line> — <finding> — <reason>

## Deferred
- <file:line> — <finding> — <where tracked>

Before reporting Declined, ask: would I defend this skip to the reviewer?
If your defense is "it was marked Consider," go back and evaluate.