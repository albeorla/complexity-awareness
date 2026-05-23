# complexity-awareness

A Claude Code plugin that adds lightweight sensitivities for handling *complex* coding tasks — the ones where your mental model keeps being wrong, where the system surprises you, where the same fix keeps not working.

It does **not** fire on routine work. Most coding tasks don't need it. The plugin is designed to be invisible until a task crosses into terrain where the normal plan-execute working mode breaks down.

## What's in it

- **`complex-task-mode` skill** — loads when a task shows complexity markers (unfamiliar codebase, surprises in system behavior, weak mental model). Shifts the working mode from planning to probing.
- **`stuck-recovery` skill** — loads when an approach has failed multiple times in the same direction. Provides a menu of genuinely different strategies to switch to, rather than refining the failing one.
- **`second-opinion` subagent** — fresh-context examiner for problems where the main agent's reasoning chain has accumulated too many assumptions to see clearly.

## What's not in it (and why)

- **No hooks.** Hooks are deterministic, and the behaviors here require judgment. A hook that forced verification every N tool calls would create exactly the procedural overhead this plugin is trying to prevent.
- **No mandatory diagnostics.** The plugin doesn't add a "first, assess complexity" step to every task. That would be ceremony on the 90% of tasks that don't need it.
- **No vocabulary.** The agent isn't asked to announce "entering complex mode" or use any framework terms. The instincts are the point; the names aren't.

## Installation

Standard Claude Code plugin install. From inside Claude Code:

```
/plugin marketplace add albeorla/complexity-awareness
/plugin install complexity-awareness@complexity-awareness
```

After installing, optionally add the block from `CLAUDE_MD_ADDENDUM.md` to your project's `CLAUDE.md` to make the skills more likely to trigger when they should.

## Design notes

The plugin's design constraint is that it must not slow down routine work. If you find it firing on tasks that turned out to be straightforward, the skill descriptions need tightening, not the skill contents. Open an issue.
