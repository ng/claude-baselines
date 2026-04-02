# claude-baselines

Starter templates for `CLAUDE.md` and supporting docs. Drop into any project to bootstrap AI-assisted development with Claude Code.

## Design principles

These principles are extracted from Claude Code's own source (its internal `agent.md`, `Skill.md`, and `docs/` structure).

### 1. Layered hierarchy

Three tiers of documentation, each serving a different purpose:

| File | Loaded | Purpose | Target length |
|------|--------|---------|---------------|
| `CLAUDE.md` | Every turn | Operating rules, commands, architecture overview | 30-60 lines |
| `.claude/docs/architecture.md` | On demand | System design, data flow, service catalog | As needed |
| `.claude/docs/conventions.md` | On demand | Naming, patterns, testing, CI | As needed |

`CLAUDE.md` is always in context. Everything else is pulled when relevant. Keep the top layer tight.

### 2. Tables over prose

Tables are scannable, diffable, and less likely to go stale than paragraphs. Use them for:
- Architecture maps (layer / path / purpose)
- Naming conventions (element / rule / example)
- Commands (task / command)
- Environment differences (aspect / dev / staging / prod)
- External services (service / client location / purpose)

### 3. "Match nearby files" over prescriptive rules

Don't try to encode every style rule. Instead:
> "Read before write. Study nearby files and match existing patterns."

This one line replaces pages of style documentation and never goes stale.

### 4. Document what exists, not what you wish existed

Every pattern in these docs should be derived from reading the actual codebase — not from aspirational best practices. If the codebase uses three different export styles, document all three. Don't pretend there's one true way.

### 5. Validate at boundaries, trust internals

Tell the agent where the system boundaries are (API inputs, env vars, webhooks) so it validates there. Everywhere else, trust the types and internal guarantees.

### 6. Living documentation clause

End with an implicit contract: these docs track the codebase, not the other way around. When patterns change, update the docs.

## Usage

### New project

```bash
# Copy templates into your project
cp templates/CLAUDE.md /path/to/project/CLAUDE.md
mkdir -p /path/to/project/.claude/docs
cp templates/architecture.md /path/to/project/.claude/docs/architecture.md
cp templates/conventions.md /path/to/project/.claude/docs/conventions.md
```

Then fill in the `{placeholders}` by reading your actual codebase. Don't guess — run `ls src/`, read config files, check the linter rules.

### Existing project

If you already have a `CLAUDE.md`, use these templates to audit what's missing. The most common gaps:
- No architecture table (agents waste tokens exploring the directory tree)
- Prose where a table would do (harder to scan, goes stale faster)
- Aspirational rules that don't match the code (agents get confused)
- Missing command reference (agents guess wrong commands)

## What NOT to put in CLAUDE.md

- **Code patterns derivable from reading files** — "match nearby files" handles this
- **Git history or recent changes** — `git log` is authoritative
- **Debugging recipes** — the fix is in the code, the context is in the commit
- **Ephemeral state** — use tasks or plans for in-progress work
- **Duplicate of README.md** — CLAUDE.md is for the agent, README is for humans

## File placement

```
project-root/
├── CLAUDE.md                    # Always loaded (keep short)
└── .claude/
    └── docs/
        ├── architecture.md      # Deep reference (loaded on demand)
        └── conventions.md       # Deep reference (loaded on demand)
```

## Templates

- [`templates/CLAUDE.md`](templates/CLAUDE.md) — Top-level operating guide
- [`templates/architecture.md`](templates/architecture.md) — System design reference
- [`templates/conventions.md`](templates/conventions.md) — Naming, patterns, testing
