# Skill Specification

This document defines the canonical format for skills in this repository.

## 1. What is a skill?

A skill is a reusable set of instructions that helps an agent perform a bounded class of tasks consistently. A skill is not a general-purpose system prompt, a transcript, a project memory dump, or a collection of unrelated tips.

## 2. Required location

```text
categories/<category>/<skill-id>/
└── SKILL.md
```

Use one of the existing categories unless there is a strong reason to add another.

## 3. Required frontmatter

Every `SKILL.md` starts with YAML frontmatter:

```yaml
---
name: skill-id
description: A concise description of the capability and when to use it.
---
```

Requirements:
- `name` must match the directory name and registry ID.
- Use lowercase kebab-case.
- `description` must explain both the task scope and activation conditions.
- Do not put secrets or personal information in metadata.

## 4. Recommended body structure

Use only sections relevant to the skill, but preserve this order where applicable:

1. **Purpose** — the specific outcome this skill supports.
2. **When to use** — positive activation conditions.
3. **When not to use** — exclusions and handoff conditions.
4. **Inputs** — information or permissions required.
5. **Procedure** — ordered, actionable steps.
6. **Output format** — expected deliverable and completion criteria.
7. **Safety and boundaries** — confirmation gates, prohibited actions, and data handling.
8. **Failure handling** — what to do when information, tools, or permissions are missing.
9. **References** — links to supporting files, if any.

## 5. Progressive disclosure and context budget

- Keep the top-level skill file focused; target roughly 100–300 lines, not as a hard limit.
- Put large reference tables, examples, schemas, and domain background in separate files under `references/`.
- Load supporting files only when the current task needs them.
- Avoid repeating global agent rules that belong in the host agent's system instructions.
- Prefer checklists and concise decision rules over long explanatory prose.
- Do not include unrelated skills in one file.

## 6. Portability

- Write vendor-neutral instructions by default.
- If a skill depends on a specific tool or platform, declare that dependency and provide a fallback where practical.
- Do not assume that every agent can execute shell commands, browse the web, access local files, or call external services.
- Distinguish instructions from executable scripts. Scripts must document runtime and dependencies.

## 7. Quality requirements

A skill must be:
- **Bounded:** one recognizable job, with clear exclusions.
- **Actionable:** steps can be followed without guessing.
- **Grounded:** no invented facts, tool capabilities, or success claims.
- **Safe:** consequential actions have explicit authorization gates.
- **Verifiable:** completion can be checked against observable criteria.
- **Maintainable:** no needless duplication; references are linked and scoped.

## 8. Registry

Every published skill must have one entry in `registry/skills.json`. The registry is discovery metadata, not a substitute for the skill's full instructions.
