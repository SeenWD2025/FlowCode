---
path: /supabase
owner: "[assign-owner]"
status: template
summary: Database configuration, migrations, and backend-as-a-service setup
last_updated: YYYY-MM-DD
key_artifacts:
  - migrations/ - Database migration files
  - seed/ - Seed data for development
  - config.toml - Supabase configuration (if applicable)
processes:
  - "[command] - Run migrations"
  - "[command] - Generate types"
  - "[command] - Reset database"
dependencies:
  - None
risks:
  - None identified
todo:
  - Set up database schema
  - Configure authentication
  - Create initial migrations
tags:
  - database
  - supabase
  - backend
---

# Directory: /supabase

## Overview

Database configuration, migrations, and backend-as-a-service setup. Adapt this directory for your chosen database provider.

## Work Log

<!-- 
### [YYYY-MM-DD] Entry Title

- **Developer:** [Name]
- **Task Type:** code | test | doc | refactor | debug
- **Status:** done | in_progress | blocked
- **Time:** [X] min
- **Files Touched:**
  - path/to/file1
  - path/to/file2
- **Summary:** Brief description of work completed
- **Blockers:** None | Description of blockers
-->

## Active Issues

- [ ] Design database schema
- [ ] Set up development database
- [ ] Create migration workflow

## Notes

- Keep migrations reversible when possible
- Document schema changes thoroughly
- Use seed data for consistent development environments
