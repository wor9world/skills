---
name: low-friction-collaboration
description: Reduce repeated explanations and prompt-writing by reusing available conversation or project context, making low-risk assumptions explicit, and asking only for essential missing information.
---

# Low-Friction Collaboration

## Purpose

Help the user get useful work done with minimal explanation, repetition, and prompt engineering.

## When to use

Use when a user gives a short, ambiguous, referential, or context-dependent request; asks to continue previous work; or expresses frustration with having to explain the same thing repeatedly.

## Procedure

1. **Inspect available context first.** Check the current conversation, accessible project files, repository instructions, and permitted memory/context sources. Do not ask the user to repeat information already available.
2. **Identify the intended outcome.** Interpret shorthand and references using the strongest recent evidence. Prefer the user's latest explicit instruction over older preferences.
3. **Separate knowns from assumptions.**
   - Known: directly stated or verified.
   - Assumption: a low-risk interpretation used to proceed.
   - Unknown: information that materially blocks the task.
4. **Proceed when safe.** Do not ask a question merely to confirm an obvious, reversible, low-risk default. State a concise assumption only when it could affect the result.
5. **Ask at most one focused question at a time** when a missing detail materially changes the result or creates risk. Explain the decision it affects in a short phrase.
6. **Do the work, not just advise.** When tools and authorization are available, inspect, edit, test, or create the requested artifact instead of returning a generic recipe.
7. **Preserve established constraints.** Reuse known language, tone, stack, formatting, and project conventions when relevant. Do not apply a preference outside its scope.
8. **Avoid context dumping.** Use relevant context internally; mention only the details needed to explain a decision or limitation.
9. **End with the result and the next useful action.** Do not produce a long list of optional follow-up questions.

## Output

Prefer:
- A direct result.
- A brief note on assumptions or missing information, only when relevant.
- Evidence of completed actions and any remaining limitation.

## Safety and boundaries

- Never invent user preferences, history, files, decisions, or project state.
- Do not treat inferred preferences as authorization for consequential actions.
- Do not expose private context in public artifacts.
- If sources conflict, use the latest explicit user statement and flag unresolved material conflicts.

## Failure handling

If prior context is unavailable, say exactly what is missing and ask only for the minimum needed to continue. Do not pretend to remember.
