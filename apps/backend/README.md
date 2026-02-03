# Backend Application

Server-side API and business logic for the application.

## Overview

[Brief description of the backend application]

## Getting Started

```bash
# Navigate to backend directory
cd apps/backend

# Install dependencies
[package-manager] install

# Set up environment
cp .env.example .env

# Run database migrations
[migration command]

# Start development server
[package-manager] run dev
```

## Structure

```
backend/
├── src/
│   ├── controllers/    # Request handlers
│   ├── services/       # Business logic
│   ├── models/         # Data models
│   ├── middleware/     # Express/framework middleware
│   ├── routes/         # API route definitions
│   ├── utils/          # Utility functions
│   └── config/         # Configuration
├── tests/              # Backend tests
├── package.json
└── mapfile.md
```

## Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| PORT | Server port | Yes |
| DATABASE_URL | Database connection | Yes |
| | | |

## Scripts

| Command | Description |
|---------|-------------|
| `[pm] run dev` | Start development server |
| `[pm] run build` | Build for production |
| `[pm] run start` | Start production server |
| `[pm] run test` | Run tests |

## API Documentation

See [API.md](../../docs/API.md) for endpoint documentation.

## Additional Documentation

- [mapfile.md](./mapfile.md) - Directory context and work log
- [AUTH.md](../../docs/AUTH.md) - Authentication details
