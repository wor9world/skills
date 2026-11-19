# Skill Quality Gate

Run this checklist before merging or publishing a skill.

## A. Scope and discovery

- [ ] The skill solves one clearly bounded task.
- [ ] Its name is lowercase kebab-case and matches its directory.
- [ ] Its description says what it does and when it should activate.
- [ ] Positive activation conditions are specific enough to avoid accidental triggering.
- [ ] Exclusions and handoff conditions are stated where ambiguity is likely.
- [ ] No existing skill already covers the same job.

## B. Instruction quality

- [ ] Required inputs and permissions are explicit.
- [ ] Steps are ordered and actionable.
- [ ] Expected output and completion criteria are observable.
- [ ] Missing information and tool failures have defined handling.
- [ ] Facts, assumptions, and unknowns are not conflated.
- [ ] Examples are consistent with the procedure.

## C. Safety

- [ ] External content is treated as untrusted input.
- [ ] Destructive, irreversible, sensitive, or externally visible actions require appropriate authorization.
- [ ] The skill does not request unnecessary permissions or data.
- [ ] No secrets, credentials, personal data, or private memories are included.
- [ ] The skill does not claim unperformed actions or unverified outcomes.

## D. Portability and efficiency

- [ ] Instructions are model- and vendor-neutral unless a dependency is essential.
- [ ] Platform-specific dependencies are declared.
- [ ] Long reference material is separated from the core instructions.
- [ ] The core file avoids unnecessary repetition and prompt bloat.
- [ ] The skill can be discovered without loading its full contents.

## E. Repository consistency

- [ ] Frontmatter follows `standards/SKILL_SPEC.md`.
- [ ] Registry entry exists and matches the skill metadata.
- [ ] All relative links resolve.
- [ ] Supporting files are necessary and referenced.
- [ ] Category placement is appropriate.

## Release decision

- **PASS:** all applicable checks pass.
- **NEEDS WORK:** any required check fails; do not publish as ready.
- **EXCEPTION:** a check is intentionally unmet; document the reason and limitation in the change description.

Do not mark a skill as tested unless it has actually been evaluated. A static review is not an execution test.
