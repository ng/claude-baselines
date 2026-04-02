# {Project Name}

{One-line description of what this project does.}

## Stack

{Runtime} · {Framework} · {Language} · {ORM/DB} · {Auth} · {Infra} · {UI lib} · {Package manager} · {Test framework} · {Deploy target}

## Core rules

- Read before write. Study nearby files and match existing patterns.
- Smallest viable change. Don't refactor adjacent code while fixing a bug or adding a feature.
- Validate at system boundaries only (user input, API payloads, env vars, webhooks). Trust internal code.
- No speculative abstractions. Three similar lines is better than a premature helper.
- Comments only when the logic isn't self-evident. Don't add docstrings to code you didn't change.
- Explicit over clever. Prefer readable logic over compact tricks.

{Add project-specific rules below — linter flags, export restrictions, import conventions, etc.}

## Commands

| Task | Command |
|------|---------|
| Dev server | `{package_manager} dev` |
| Type check | `{package_manager} tsc` |
| Lint | `{package_manager} lint` |
| Tests | `{package_manager} test` |
| Build | `{package_manager} build` |

{Add project-specific commands (migrations, codegen, deploy, etc.)}

## Architecture at a glance

| Layer | Path | Purpose |
|-------|------|---------|
| {layer} | `{path}/` | {one-line purpose} |

{Map every top-level src/ directory. One row per directory. This table is the single most useful thing for agent orientation.}

See [.claude/docs/architecture.md](.claude/docs/architecture.md) and [.claude/docs/conventions.md](.claude/docs/conventions.md) for deeper reference.
