# CLAUDE.md addendum — complexity awareness

Copy the following block into your project's CLAUDE.md if you want the complexity-awareness skills to fire reliably. The skills handle the heavy lifting; this block makes the agent more likely to notice when to invoke them.

---

## When tasks get hard

Most tasks here have a clear right answer findable through normal work. Some don't — debugging unfamiliar code, large refactors, designing under unclear constraints. When you notice the system is surprising you, your mental model keeps being wrong, or the same approach is failing repeatedly, that's a signal to shift modes rather than push harder.

Specifically:

- When the task feels exploratory or your model of the system feels weak, invoke the `complex-task-mode` skill before continuing.
- When an approach has failed twice in the same direction, invoke the `stuck-recovery` skill before trying it a third time.
- Don't respond to difficulty by adding ceremony — more confirmation prompts, longer plans, more cautious edits. Difficulty usually means a premise is wrong, not that execution needs more care.
