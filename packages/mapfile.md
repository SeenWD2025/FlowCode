---
path: /packages
owner: "[assign-owner]"
status: template
summary: Publishable packages and shared dependencies
last_updated: YYYY-MM-DD
key_artifacts:
  - "[package-name]/ - Description of package"
processes:
  - "[command] - Build all packages"
  - "[command] - Publish packages"
  - "[command] - Link packages locally"
dependencies:
  - None
risks:
  - None identified
todo:
  - Define package structure
  - Set up package publishing
tags:
  - packages
  - shared
  - monorepo
---

# Directory: /packages

## Overview

Publishable packages for monorepo architecture. Shared code that can be versioned and published independently.

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

- [ ] Define package structure conventions
- [ ] Set up build tooling for packages

## Notes

- Each package should have its own README, package.json, and mapfile.md
- Use semantic versioning for published packages
- Document public APIs thoroughly
