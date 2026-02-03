---path: /apps
owner: "[assign-owner]"
status: template
summary: Application modules - frontend and backend deployable units
last_updated: YYYY-MM-DD
key_artifacts:
  - frontend/ - Client-side application
  - backend/ - Server-side application
  - libs/ - Shared code between apps (if applicable)
processes:
  - "[command] - Start all apps in development"
  - "[command] - Build all apps for production"
dependencies:
  - /packages - Shared packages
  - /supabase - Database and auth (if applicable)
risks:
  - None identified
todo:
  - Initialize frontend framework
  - Initialize backend framework
tags:
  - apps
  - core
---

# Directory: /apps

## Overview

This directory contains all deployable application code. Frontend and backend applications live here as separate modules, with shared code in the `libs/` subdirectory.

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

- [ ] Initialize frontend framework
- [ ] Initialize backend framework
- [ ] Set up shared libs structure

## Notes

- Each app should have its own `package.json` and can be developed independently
- Shared code between frontend and backend goes in `libs/`
- Follow the mapfile pattern in each subdirectory