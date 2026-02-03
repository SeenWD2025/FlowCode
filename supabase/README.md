# Database Configuration

Database setup, migrations, and backend-as-a-service configuration.

## Overview

[Describe database strategy - Supabase, PostgreSQL, MySQL, etc.]

> **Note:** This directory is named `supabase/` as a default. Rename or restructure for your chosen database solution.

## Structure

```
supabase/  (or database/)
├── migrations/         # Database migration files
│   └── YYYYMMDDHHMMSS_[description].sql
├── seed/               # Seed data for development
│   └── seed.sql
├── functions/          # Database functions (if applicable)
├── config.toml         # Configuration (if using Supabase)
└── mapfile.md
```

## Getting Started

### Prerequisites

- [ ] Database server installed/accessible
- [ ] Database client installed
- [ ] Environment variables configured

### Setup

```bash
# Initialize database
[init command]

# Run migrations
[migration command]

# Seed development data
[seed command]
```

## Common Commands

| Command | Description |
|---------|-------------|
| `[pm] run db:migrate` | Run pending migrations |
| `[pm] run db:rollback` | Rollback last migration |
| `[pm] run db:seed` | Seed database with test data |
| `[pm] run db:reset` | Reset database (dev only) |
| `[pm] run db:generate-types` | Generate TypeScript types |

## Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| DATABASE_URL | Connection string | postgresql://... |
| | | |

## Migrations

See [MIGRATIONS.md](../docs/MIGRATIONS.md) for migration guidelines.

## Additional Documentation

- [mapfile.md](./mapfile.md) - Directory context and work log
- [MIGRATIONS.md](../docs/MIGRATIONS.md) - Migration procedures
- [STORAGE.md](../docs/STORAGE.md) - Storage documentation
