# Architecture

## Request flow

{Diagram or description of how a request moves through the system. Use ASCII art or a simple list.}

```
Client → Auth → {Router/Middleware} → {Handler} → {Data layer}
                                    → {External service}
                                    → {Background job}
```

## Authentication & authorization

| Wrapper/Middleware | Location | Purpose |
|--------------------|----------|---------|
| {name} | `{path}` | {what it checks, what it provides downstream} |

{Describe auth flow: how tokens are validated, how user identity propagates, role hierarchy.}

## Data layer

### Key tables/collections

| Table | Key columns | Notes |
|-------|-------------|-------|
| {name} | {important fields} | {status lifecycle, relationships, constraints} |

### Conventions

{DB-specific patterns: naming (snake_case vs camelCase), timestamps, soft deletes, enums, JSON columns, index strategy.}

## API design

### Envelope

```typescript
// Define your standard response shape here
{ ok: true, data: T }
{ ok: false, error: { code: string, message: string } }
```

### Versioning

{How API versions are managed: URL prefix, headers, etc.}

## External services

| Service | Client location | Purpose |
|---------|----------------|---------|
| {name} | `{path}` | {what it does} |

{Map every external dependency: cloud services, third-party APIs, queues, etc.}

## Environments

| Aspect | Development | Staging | Production |
|--------|-------------|---------|------------|
| DB | {local/branch} | {staging instance} | {prod instance} |
| Deploy | `localhost` | {staging URL} | {prod URL} |
| {aspect} | {value} | {value} | {value} |

{Include any env resolution logic, feature flags, or environment-specific behaviors.}
