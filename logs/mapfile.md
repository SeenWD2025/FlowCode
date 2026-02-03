---
path: /logs
owner: "[assign-owner]"
status: template
summary: Development logs, decision records, and session notes
last_updated: YYYY-MM-DD
key_artifacts:
  - sessions/ - Development session logs
  - decisions/ - Architecture Decision Records (ADRs)
processes:
  - Create new session log for each development session
  - Document significant decisions in ADR format
dependencies:
  - None
risks:
  - None identified
todo:
  - Establish logging conventions
  - Create ADR template
tags:
  - logs
  - documentation
  - decisions
---

# Directory: /logs

## Overview

Development logs, session notes, and Architecture Decision Records (ADRs). This directory maintains project history and rationale for decisions.

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

- [ ] Define session log template
- [ ] Define ADR template

## Notes

- Log significant development sessions
- Document architectural decisions with context and rationale
- Keep logs chronological for easy reference
