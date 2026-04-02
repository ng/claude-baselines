# Conventions

## Naming

| Element | Rule | Example |
|---------|------|---------|
| Components | {PascalCase / kebab-case} | `{example}` |
| Utilities | {kebab-case / camelCase} | `{example}` |
| Hooks | `use` + PascalCase | `{example}` |
| DB tables | {snake_case / camelCase} | `{example}` |
| DB columns | {snake_case / camelCase} | `{example}` |
| Test files | {naming pattern} | `{example}` |
| Type interfaces | {naming pattern} | `{example}` |
| Constants | {SCREAMING_SNAKE / camelCase} | `{example}` |

{Add rows for any naming patterns specific to the project: dialogs, services, API types, etc.}

## File organization

{Describe the organizing principle: feature-based, type-based, or hybrid. Show the directory tree of the main code directory.}

```
src/
├── {dir}/    # {purpose}
├── {dir}/    # {purpose}
└── {dir}/    # {purpose}
```

### Barrel exports

{Describe the export pattern used: named, default, mixed, or "no barrels."}

## Component patterns

{Document the 2-3 most common UI patterns with minimal code examples. Only include patterns that are actually repeated across the codebase — don't prescribe patterns that don't exist yet.}

## API patterns

{How route handlers are structured: auth wrappers, validation, response formatting. Show a real pattern, not an aspirational one.}

## Testing

- **Framework**: {name}
- **Location**: {where tests live relative to source}
- **Coverage philosophy**: {what gets tested and what doesn't}

## Import conventions

{Import sorting rules, path aliases, type-only imports, any ESLint enforcement.}

## Git & CI

{Branch strategy, CI pipeline stages, auto-merge rules, commit message conventions — only if non-obvious or enforced by tooling.}
