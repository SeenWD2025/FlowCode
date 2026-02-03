---
path: /dev-tools
owner: "[assign-owner]"
status: template
summary: Development tools, IDE configs, and local environment setup
last_updated: YYYY-MM-DD
key_artifacts:
  - update-root-mapfile.js - Script to regenerate root-mapfile.md
  - "[config-file] - Description"
processes:
  - "node dev-tools/update-root-mapfile.js - Regenerate project map"
dependencies:
  - None
risks:
  - None identified
todo:
  - Add IDE configuration templates
  - Document local setup scripts
tags:
  - dev-tools
  - configuration
  - utilities
---

# Directory: /dev-tools

## Overview

Development tools, IDE configurations, and local environment setup scripts. These tools support the development workflow.

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

- [ ] Document available tools
- [ ] Add setup automation scripts

## Notes

- Keep dev tools cross-platform when possible
- Document any system dependencies required
- Update-root-mapfile.js should be run after adding new directories
