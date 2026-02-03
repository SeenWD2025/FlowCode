---
path: /tests
owner: "[assign-owner]"
status: template
summary: End-to-end, integration, and system test suites
last_updated: YYYY-MM-DD
key_artifacts:
  - unit/ - Unit tests
  - integration/ - API and service integration tests
  - system/ - System-level tests
  - acceptance/ - User acceptance tests
processes:
  - "[command] - Run all tests"
  - "[command] - Run unit tests"
  - "[command] - Run integration tests"
  - "[command] - Run with coverage"
dependencies:
  - /apps - Application code to test
risks:
  - None identified
todo:
  - Set up test framework
  - Create test utilities
  - Define test conventions
tags:
  - tests
  - qa
  - testing
---

# Directory: /tests

## Overview

Test suites organized by type. Contains unit, integration, system, and acceptance tests.

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

- [ ] Choose test framework
- [ ] Set up test infrastructure
- [ ] Create test utilities and fixtures

## Notes

- Follow the testing pyramid: many unit tests, fewer integration tests
- Keep tests isolated and independent
- Use descriptive test names that explain the expected behavior

