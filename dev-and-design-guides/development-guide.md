# Development Guide

## Getting Started

### Prerequisites
- Node.js version: 
- Package manager: 
- Database: 
- Other tools: 

### Initial Setup
```bash
# Clone the repository
git clone <repository-url>

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env

# Start development server
npm run dev
```

---

## Project Architecture

### Tech Stack
| Layer | Technology | Purpose |
|-------|------------|---------|
| Frontend | | |
| Backend | | |
| Database | | |
| Authentication | | |
| Hosting | | |

### Directory Structure Philosophy
- `/apps` - Application code (frontend, backend)
- `/packages` - Shared packages and libraries
- `/apps/libs` - Shared utilities within apps
- `/scripts` - Build and automation scripts
- `/docs` - Documentation
- `/tests` - Test suites

---

## Code Standards

### Naming Conventions
| Type | Convention | Example |
|------|------------|---------|
| Files (components) | PascalCase | `UserProfile.tsx` |
| Files (utilities) | kebab-case | `date-utils.ts` |
| Functions | camelCase | `getUserById()` |
| Constants | UPPER_SNAKE | `MAX_RETRY_COUNT` |
| Types/Interfaces | PascalCase | `UserProfile` |
| CSS classes | kebab-case | `user-profile` |

### File Organization
```
component/
├── ComponentName.tsx       # Main component
├── ComponentName.test.tsx  # Tests
├── ComponentName.styles.ts # Styles (if separate)
├── index.ts               # Public exports
└── types.ts               # Component-specific types
```

---

## Git Workflow

### Branch Naming
- `main` - Production-ready code
- `develop` - Integration branch
- `feature/<ticket-id>-description` - New features
- `bugfix/<ticket-id>-description` - Bug fixes
- `hotfix/<ticket-id>-description` - Production hotfixes

### Commit Messages
Follow conventional commits:
```
type(scope): description

[optional body]

[optional footer]
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

### Pull Request Process
1. Create feature branch from `develop`
2. Make changes with atomic commits
3. Push and create PR
4. Ensure CI passes
5. Request review
6. Address feedback
7. Merge after approval

---

## Environment Configuration

### Environment Files
- `.env.example` - Template with all variables
- `.env.local` - Local development (gitignored)
- `.env.test` - Test environment
- `.env.production` - Production values (in CI/CD)

### Required Variables
```env
# App
NODE_ENV=development
APP_URL=http://localhost:3000

# Database
DATABASE_URL=

# Authentication
AUTH_SECRET=

# External Services
API_KEY=
```

---

## Testing Strategy

### Test Types
| Type | Location | Purpose |
|------|----------|---------|
| Unit | `*.test.ts` | Individual functions |
| Integration | `/tests/integration` | Component interaction |
| E2E | `/tests/e2e` | Full user flows |

### Running Tests
```bash
# Run all tests
npm test

# Run with coverage
npm run test:coverage

# Run e2e tests
npm run test:e2e
```

### Coverage Targets
- Statements: 80%
- Branches: 75%
- Functions: 80%
- Lines: 80%

---

## API Design

### REST Conventions
- Use plural nouns for resources: `/users`, `/posts`
- Nest related resources: `/users/:id/posts`
- Use query params for filtering: `/users?status=active`
- Return appropriate status codes

### Response Format
```json
{
  "success": true,
  "data": {},
  "meta": {
    "pagination": {}
  },
  "error": null
}
```

---

## Error Handling

### Frontend
- Use error boundaries for React
- Display user-friendly messages
- Log errors to monitoring service

### Backend
- Use consistent error response format
- Include error codes for client handling
- Never expose stack traces in production

---

## Performance Guidelines

### Frontend
- Lazy load routes and heavy components
- Optimize images and assets
- Minimize bundle size
- Use caching strategies

### Backend
- Implement database query optimization
- Use connection pooling
- Cache frequently accessed data
- Rate limit API endpoints

---

## Security Checklist

- [ ] Input validation on all endpoints
- [ ] SQL injection prevention (parameterized queries)
- [ ] XSS prevention (sanitize outputs)
- [ ] CSRF protection
- [ ] Secure headers configured
- [ ] Secrets in environment variables
- [ ] HTTPS enforced
- [ ] Authentication properly implemented
- [ ] Authorization checks on resources

---

## Debugging

### Tools
- Browser DevTools
- VS Code debugger
- Database GUI: 

### Logging
- Development: Console output
- Production: Structured logging to service

---

## Deployment

### Environments
| Environment | URL | Branch | Auto-deploy |
|-------------|-----|--------|-------------|
| Development | | develop | Yes |
| Staging | | main | Yes |
| Production | | main (tag) | Manual |

### Deployment Checklist
- [ ] All tests passing
- [ ] Build succeeds
- [ ] Environment variables set
- [ ] Database migrations run
- [ ] Monitoring configured

---

## Mapfile Pattern

Each directory contains a `mapfile.md` with YAML frontmatter for project navigation:

```yaml
---
path: /apps/frontend
owner: team-frontend
status: active
summary: React frontend application
last_updated: 2024-01-01
key_artifacts:
  - src/App.tsx
processes:
  - npm run dev
dependencies:
  - react
  - typescript
risks:
  - None identified
todo:
  - Complete auth flow
tags: [frontend, react]
---
```

Run `node scripts/update-root-mapfile.js` to regenerate the project map.
