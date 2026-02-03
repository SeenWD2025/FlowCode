---
path: /apps/backend
owner: "[assign-owner]"
status: template
summary: Server-side API and business logic
last_updated: YYYY-MM-DD
key_artifacts:
  - src/ - Source code
  - package.json - Dependencies and scripts
processes:
  - "[command] - Start development server with hot reload"
  - "[command] - Compile for production"
  - "[command] - Run production server"
  - "[command] - Run tests"
dependencies:
  - /apps/libs - Shared utilities (if applicable)
  - /supabase - Database connection (if applicable)
risks:
  - None identified
todo:
  - Choose and initialize backend framework
  - Set up database connection
  - Configure authentication middleware
  - Define API routes structure
tags:
  - backend
  - api
  - server
---

# Directory: /apps/backend

## Overview

Server-side application containing API endpoints, business logic, and data access layers.

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

- [ ] Choose backend framework
- [ ] Set up project structure
- [ ] Configure database connection

## Notes

- Keep business logic separate from API route handlers
- Follow RESTful conventions for API design
- Document all endpoints in /docs/API.md
