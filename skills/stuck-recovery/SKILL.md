---
name: stuck-recovery
description: Use when an approach has failed two or more times in the same direction — repeated test failures despite "fixes," the same error after multiple attempts, edits that don't produce expected behavior, or a growing sense that you're patching rather than solving. Do not use on first failure (normal iteration) or for routine debugging where each iteration reveals new information. The signal is "I'm doing variations of the same thing and getting variations of the same failure."
---

# Stuck-recovery

You're in this skill because the same approach has failed multiple times. The reflexive response — try the same thing with more care, add more procedure, retry with small tweaks — is exactly wrong. Repeated failure in one direction means a premise is wrong, not that the execution is wrong.

## First: stop adding procedure

Before switching strategy, notice if you've been responding to failure with more ceremony — more confirmation steps, longer plans, more cautious edits. That is the over-correction this skill is preventing. Adding governance does not fix a strategy mismatch. It just makes the failure slower.

## Then: switch to a genuinely different strategy

Pick from this menu. The strategies are deliberately different from each other — not variations of the same approach.

**1. Shrink the problem.** Find the smallest version of the failure you can reproduce. Often the smallest version reveals what the full-size version was hiding.

**2. Verify a premise.** Make an explicit list of what you're assuming to be true. Pick the assumption you're least sure of and check it directly. One of your premises is almost certainly wrong; the question is which one.

**3. Change abstraction level.** If you've been working at the function level, look at the module or the data flow. If you've been thinking architecturally, look at the actual lines that execute. Stuck-ness often means you're at the wrong altitude.

**4. Direct inspection.** Stop reasoning about what the code does and read what it does. Run it. Print intermediate state. Look at actual values, not your model of values.

**5. Adversarial reading.** Instead of asking "how do I make this work," ask "why is this failing?" Read the failure literally. The error message often says exactly what's wrong, but you've been reading past it.

**6. Restart with a fresh frame.** Sometimes the way the problem was defined is the problem. Re-describe what you're trying to accomplish, without using any of the language from the failed attempts. See if the new framing suggests a different approach.

**7. Surface to the user.** Sometimes the missing input is human judgment, not more code. If the user has context you don't (intent, history, constraints), keep going is the wrong move. Ask.

**8. Hand off to second-opinion agent.** If you've tried switching strategies and you're still stuck, invoke the `second-opinion` subagent. The fresh context window is the point — your current reasoning chain has accumulated assumptions you can't see anymore.

## Pick fast, commit fast

Don't deliberate at length about which strategy to switch to. The value is in the switch, not in picking optimally. Pick the one that contradicts your current approach most directly and try it.

## What this skill is *not* asking you to do

- Don't enumerate all strategies for the user. Pick one and try it.
- Don't apologize or narrate the switch heavily. Just switch.
- Don't treat "switch strategies" as itself a procedure to follow rigorously. It's a release valve, not a ritual.
