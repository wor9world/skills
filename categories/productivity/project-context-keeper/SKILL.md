---
name: project-context-keeper
description: Maintain accurate project continuity by extracting constraints and decisions from authoritative project sources, detecting stale context, and producing compact handoffs without inventing status.
---

# Project Context Keeper

## Purpose

Reduce repeated project explanations while preventing stale notes, guesses, and unrelated project details from contaminating current work.

## When to use

Use when continuing a project across sessions, onboarding an agent to a repository, preparing a handoff, summarizing project status, or deciding the next implementation step.

## Source priority

Prefer evidence in this order:
1. Current user instruction.
2. Current repository state, source code, tests, and project documentation.
3. Explicitly dated project status supplied by the user.
4. Recent conversation decisions.
5. Older summaries or inferred context.

A newer source does not automatically override a more authoritative source; explain material conflicts.

## Procedure

1. Identify the project and the exact task. Do not merge context from similarly named or unrelated projects.
2. Inspect available project instructions and relevant files before relying on memory.
3. Extract only information needed for the current task:
   - Purpose and current state.
   - Stack and version constraints.
   - Architecture and key interfaces.
   - Explicit decisions and rejected alternatives.
   - Known defects, risks, and blockers.
   - Next agreed action.
4. Attach dates or source locations to status claims when available.
5. Mark each item as verified, user-reported, inferred, stale, or unknown.
6. Preserve exact constraints. Do not silently normalize versions, paths, names, or technical decisions.
7. Detect contradictions and ask only when the conflict changes the implementation.
8. Produce a compact handoff that another agent can use without loading the entire conversation.
9. Update project documentation only when requested or clearly within the authorized task.

## Handoff format

- **Project / task**
- **Verified current state**
- **User-stated constraints**
- **Decisions**
- **Open risks / unknowns**
- **Next action**
- **Sources and last-verified date**

## Safety and boundaries

- Never invent progress, test results, deployment status, or completed work.
- Never use an old status as current without checking its date.
- Keep project-specific or personal details in private project context, not in public generic skills.
- Do not expose credentials, tokens, private URLs, or personal data.

## Failure handling

If source files cannot be accessed, label the handoff as based on user-provided or historical context and identify what needs verification.
