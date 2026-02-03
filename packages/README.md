# Packages

Publishable packages and shared dependencies for monorepo architecture.

## Overview

This directory contains shared packages that can be versioned and published independently.

## Structure

```
packages/
├── [package-name]/
│   ├── src/            # Source code
│   ├── dist/           # Built output
│   ├── package.json    # Package configuration
│   ├── README.md       # Package documentation
│   └── mapfile.md      # Package context
└── mapfile.md
```

## Available Packages

| Package | Description | Version |
|---------|-------------|---------|
| [package-name] | [Description] | [version] |

## Creating a New Package

1. Create directory: `packages/[package-name]/`
2. Initialize package.json:
   ```bash
   cd packages/[package-name]
   [package-manager] init
   ```
3. Add `mapfile.md` with directory context
4. Add `README.md` with package documentation
5. Update workspace configuration
6. Run `node dev-tools/update-root-mapfile.js`

## Package Template

### package.json

```json
{
  "name": "@[scope]/[package-name]",
  "version": "0.0.1",
  "main": "dist/index.js",
  "types": "dist/index.d.ts",
  "scripts": {
    "build": "[build command]",
    "test": "[test command]"
  }
}
```

## Commands

```bash
# Build all packages
[package-manager] run build:packages

# Build specific package
[package-manager] run build --filter=[package-name]

# Link packages locally
[package-manager] run link
```

## Additional Documentation

- [mapfile.md](./mapfile.md) - Directory context and work log

