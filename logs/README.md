# Development Logs

Development session logs, decision records, and project history.

## Overview

This directory maintains project history, capturing work sessions and architectural decisions.

## Structure

```
logs/
├── sessions/           # Development session logs
│   └── YYYY-MM-DD.md
├── decisions/          # Architecture Decision Records (ADRs)
│   └── ADR-001-[title].md
└── mapfile.md
```

## Session Log Template

```markdown
# Session: YYYY-MM-DD

## Goals
- Goal 1
- Goal 2

## Completed
- [x] Task 1
- [x] Task 2

## Blockers
- Blocker description (if any)

## Next Steps
- Next action 1
- Next action 2

## Notes
Additional context or observations.
```

## Decision Record (ADR) Template

```markdown
# ADR-[NUMBER]: [Title]

**Date:** YYYY-MM-DD
**Status:** Proposed | Accepted | Deprecated | Superseded
**Deciders:** [Names]

## Context
What is the issue or decision we need to make?

## Decision
What is the change that we're proposing?

## Consequences

### Positive
- Benefit 1
- Benefit 2

### Negative
- Drawback 1
- Drawback 2

## Alternatives Considered
- Alternative 1: [Why rejected]
- Alternative 2: [Why rejected]
```

## Best Practices

- Create a session log for significant development sessions
- Document all architectural decisions as ADRs
- Reference ADR numbers in related code comments
- Keep logs concise but informative

## Additional Documentation

- [mapfile.md](./mapfile.md) - Directory context and work log

