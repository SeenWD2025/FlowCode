---path: /apps/frontend
owner: "[assign-owner]"
status: template
summary: Client-side web application
last_updated: YYYY-MM-DD
key_artifacts:
  - src/ - Source code
  - public/ - Static assets
  - package.json - Dependencies and scripts
processes:
  - "[command] - Start development server"
  - "[command] - Create production build"
  - "[command] - Run linter"
  - "[command] - Run tests"
dependencies:
  - /apps/libs - Shared utilities (if applicable)
  - /packages/ui - UI component library (if applicable)
risks:
  - None identified
todo:
  - Choose and initialize frontend framework
  - Set up routing
  - Configure state management
  - Establish component structure
tags:
  - frontend
  - ui
  - client
---

# Directory: /apps/frontend

## Overview

Client-side web application containing UI components, pages, and client-side logic.

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

- [ ] Choose frontend framework
- [ ] Set up project structure
- [ ] Configure build tooling

## Notes

- Follow the design-guide.md for UI consistency
- Use component-driven development
- Keep components small and reusable