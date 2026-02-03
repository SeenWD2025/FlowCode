# Frontend Application

Client-side web application.

## Overview

[Brief description of the frontend application]

## Getting Started

```bash
# Navigate to frontend directory
cd apps/frontend

# Install dependencies
[package-manager] install

# Set up environment
cp .env.example .env

# Start development server
[package-manager] run dev
```

## Structure

```
frontend/
├── src/
│   ├── components/     # Reusable UI components
│   ├── pages/          # Page components/routes
│   ├── hooks/          # Custom React hooks
│   ├── services/       # API client and services
│   ├── stores/         # State management
│   ├── styles/         # Global styles
│   └── utils/          # Utility functions
├── public/             # Static assets
├── tests/              # Frontend tests
├── package.json
└── mapfile.md
```

## Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| VITE_API_URL | Backend API URL | Yes |
| | | |

## Scripts

| Command | Description |
|---------|-------------|
| `[pm] run dev` | Start development server |
| `[pm] run build` | Build for production |
| `[pm] run preview` | Preview production build |
| `[pm] run test` | Run tests |
| `[pm] run lint` | Run linter |

## Design System

See [design-guide.md](../../dev-and-design-guides/design-guide.md) for visual standards.

## Additional Documentation

- [mapfile.md](./mapfile.md) - Directory context and work log
- [development-guide.md](../../dev-and-design-guides/development-guide.md) - Coding standards

