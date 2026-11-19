---
name: technical-spec-builder
description: Turn a short product or engineering request into an implementable specification with explicit constraints, user flows, states, contracts, acceptance criteria, and phased delivery.
---

# Technical Specification Builder

## Purpose

Convert incomplete or conversational requirements into a concrete specification that engineers or coding agents can implement without filling gaps through guesswork.

## When to use

Use when asked to design a feature, page, application, API, architecture, workflow, implementation plan, or detailed UI/UX specification.

## Procedure

1. Read the current request and recover relevant constraints from available project context and repository guidance.
2. Inspect the existing codebase or design system when access is available. Do not design against an imagined architecture.
3. Record:
   - Goals and non-goals.
   - User roles and primary workflows.
   - Required stack and versions, if supplied.
   - Data entities and typed contracts.
   - UI states, loading, empty, error, success, and disabled states.
   - Validation, permissions, and failure behavior.
   - Accessibility, responsive behavior, and keyboard interaction.
4. Separate explicit requirements from assumptions. Choose reversible defaults for minor gaps; ask one question only for a decision that blocks implementation or materially changes architecture.
5. Define acceptance criteria that can be observed or tested. Avoid vague statements such as "intuitive", "modern", or "works well" without measurable behavior.
6. Prioritize delivery into phases. Put the core end-to-end workflow first; defer polish and optional features.
7. Include dependencies, risks, migration implications, and out-of-scope work where relevant.
8. Check that every requested requirement appears in the design and acceptance criteria.
9. Keep the specification internally consistent and sufficiently detailed for implementation.

## Output structure

Use relevant sections:
1. Objective and scope
2. Constraints and assumptions
3. User flows
4. Screens/components or system modules
5. Data and type contracts
6. Interaction and state behavior
7. Errors, validation, and permissions
8. Accessibility and responsive requirements
9. Acceptance criteria
10. Phases and risks

## Safety and boundaries

- Follow the user's stated stack exactly; do not silently substitute libraries or versions.
- Do not add backend, authentication, persistence, or external services when explicitly excluded.
- Do not claim a feature exists in the current code unless inspected.
- Keep user-specific project details out of public reusable specifications.

## Failure handling

If repository inspection is unavailable, label architecture-dependent details as assumptions and write the spec so those assumptions are easy to validate.
