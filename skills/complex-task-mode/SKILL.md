---
name: complex-task-mode
description: Use when a coding task shows complexity markers — debugging an unfamiliar system, refactoring across many files in a codebase whose conventions you don't yet understand, designing a feature where constraints are still being discovered, or any task where your mental model has been wrong more than once. Do not use for well-scoped tasks with a clear right answer (typical bug fixes, isolated feature additions, well-defined refactors). The signal is "the system keeps surprising me" or "I'm not sure I'm even working on the right thing."
---

# Complex-task mode

You're in this skill because the task shows signs of being complex rather than merely complicated. The working mode shifts from plan-execute to probe-sense-respond.

## Recognize the terrain

Complex coding terrain has tells. If two or more of these are true, treat it as complex:

- You don't have a confident mental model of the system you're modifying.
- The codebase has conventions you haven't fully inferred yet.
- Your first reading of the problem turned out to be incomplete or wrong.
- Test failures or runtime behavior have surprised you more than once.
- The user's framing of the problem may itself be approximate.
- The change touches multiple subsystems that interact in ways you can't fully trace.

If only one of these is true, you're probably in complicated terrain with one uncertain element. Handle the uncertain element specifically and proceed normally.

## Work in probes, not plans

In complex terrain, your plan is provisional. You're not executing a plan; you're running a sequence of small probes, each of which teaches you something about the system.

A probe is:
- **Small** — minutes of work, not hours. Reversible if wrong.
- **Diagnostic** — designed to reveal something you currently don't know, not to make progress toward a fixed endpoint.
- **Followed by verification** — you read the actual result, not your prediction of it.

After each probe, ask: did the system behave the way I expected? If yes, your model is holding; continue. If no, your model just moved — stop and re-orient before the next action.

## Detect drift before it compounds

The most common complex-task failure is acting on a stale mental model. You believed something three actions ago that is no longer true, and you've been compounding the error since.

Drift signals:

- You're surprised by file contents when you read them.
- A test fails for a reason you can't explain from your current model.
- You catch yourself thinking "that shouldn't be possible."
- You've made several edits without reading current state or running anything.
- You're predicting what code does instead of checking.

When you notice drift: stop. Don't fix it by doing more. Read the actual current state of the relevant code or system. State out loud (in your reasoning) what you now know that you didn't before. Then decide the next probe from the new model, not the old one.

## What this skill is *not* asking you to do

- Don't narrate the framework. Don't say "I'm entering probe-sense-respond mode." Just work this way.
- Don't add procedural overhead. No mandatory checklists. No "are you sure?" prompts to the user.
- Don't ask the user to confirm every probe. Probes are your way of learning; you're allowed to run them.
- Don't slow down on tasks that turn out to be complicated after all. If the system stops surprising you and your model is holding, you're in complicated terrain again — work normally.

## You are inside the system

Your edits change the territory. The codebase after your last change is not the codebase you were modeling two changes ago. Re-read after substantive changes; don't trust your post-edit prediction of file state.
