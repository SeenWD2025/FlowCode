# Tests

Test suites for the application organized by test type.

## Overview

[Describe testing strategy and frameworks used]

## Structure

```
tests/
├── unit/               # Unit tests
├── integration/        # API and service integration tests
├── system/             # System-level tests
├── acceptance/         # User acceptance tests (E2E)
├── fixtures/           # Test data and factories
├── mocks/              # Shared mock implementations
└── mapfile.md
```

## Test Types

| Type | Location | Purpose |
|------|----------|---------|
| Unit | `unit/` | Test individual functions/components |
| Integration | `integration/` | Test API endpoints and services |
| System | `system/` | Test full system behavior |
| Acceptance | `acceptance/` | End-to-end user flows |

## Running Tests

```bash
# Run all tests
[package-manager] run test

# Run specific test type
[package-manager] run test:unit
[package-manager] run test:integration
[package-manager] run test:e2e

# Run with coverage
[package-manager] run test:coverage

# Run in watch mode
[package-manager] run test:watch

# Run specific test file
[package-manager] run test -- [path/to/test]
```

## Writing Tests

### Naming Conventions

- Test files: `[feature].test.[ext]` or `[feature].spec.[ext]`
- Describe blocks: Feature or component name
- Test cases: "should [expected behavior] when [condition]"

### Test Structure

```[language]
describe('[Feature/Component]', () => {
  beforeEach(() => {
    // Setup
  });

  it('should [expected behavior] when [condition]', () => {
    // Arrange
    // Act
    // Assert
  });
});
```

## Coverage Requirements

| Metric | Target |
|--------|--------|
| Statements | [X]% |
| Branches | [X]% |
| Functions | [X]% |
| Lines | [X]% |

## Fixtures and Mocks

### Test Fixtures

Located in `fixtures/` - reusable test data.

### Mocks

Located in `mocks/` - shared mock implementations.

## CI Integration

Tests run automatically on:
- Pull requests
- Merge to develop/main

## Additional Documentation

- [mapfile.md](./mapfile.md) - Directory context and work log
- [development-guide.md](../dev-and-design-guides/development-guide.md) - Testing standards

