# Skills

A model-independent library of reusable instructions, workflows, and domain procedures for AI agents and human operators.

The repository is designed for **progressive disclosure**: keep discovery metadata small, load a skill only when its description matches the task, and read detailed references only when needed.

## Principles

- **Model-independent:** describe behavior and interfaces without depending on one vendor or model.
- **Small by default:** concise skill instructions; move long references into `references/`.
- **Explicit activation:** a skill is selected by a clear task match, not loaded wholesale.
- **Safe execution:** distinguish advice from actions; require confirmation for destructive, external, or irreversible operations.
- **Evidence over invention:** state assumptions, verify claims, and mark unknowns.
- **Testable:** every skill has scope, inputs, outputs, failure modes, and a quality checklist.
- **No secrets:** never commit credentials, personal data, private memories, or machine-specific configuration.

## Repository map

```text
.
├── AGENTS.md                 # Instructions for contributors and AI coding agents
├── README.md
├── LICENSE
├── registry/
│   └── skills.json           # Lightweight machine-readable skill catalog
├── standards/
│   ├── SKILL_SPEC.md         # Required skill format and authoring rules
│   └── QUALITY_GATE.md       # Review and release checklist
└── categories/
    ├── engineering/
    ├── research/
    ├── reasoning/
    └── productivity/
```

Each skill lives in its category directory and has its own `SKILL.md`. Optional supporting material belongs beside it:

```text
categories/<category>/<skill-name>/
├── SKILL.md
├── references/               # Detailed material, loaded only when needed
├── scripts/                  # Optional deterministic helpers
└── tests/                    # Optional fixtures or evaluation cases
```

## How an agent should use this repository

1. Read the skill catalog or discover candidate skill descriptions.
2. Match the current task against skill names and descriptions.
3. Load only the best-matching `SKILL.md` files.
4. Load a reference file only if the skill explicitly needs it.
5. Follow the skill's safety and confirmation requirements.
6. Report uncertainty and distinguish verified facts from assumptions.

Do not load every skill into the prompt. Do not select a skill solely because its name contains a keyword; check its scope and exclusions.

## Categories

| Category | Purpose |
|---|---|
| `engineering` | Software design, implementation, debugging, testing, infrastructure |
| `research` | Source discovery, evidence collection, synthesis, technical research |
| `reasoning` | Structured analysis, decision methods, problem decomposition |
| `productivity` | Planning, documentation, communication, repeatable workflows |

Add a category only when several skills need it. Avoid creating categories for one-off skills.

## Contributing

Follow [AGENTS.md](AGENTS.md), [the skill specification](standards/SKILL_SPEC.md), and [the quality gate](standards/QUALITY_GATE.md). Add or update the registry entry whenever a skill is added, renamed, deprecated, or removed.

## License

MIT. See [LICENSE](LICENSE).
