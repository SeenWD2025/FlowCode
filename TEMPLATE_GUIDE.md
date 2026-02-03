# Template Guide

## Quick Overview

This is an **AI-Assisted Development Template** - a framework for building production-ready apps using AI agent orchestration, structured planning, and the Devn-Noble workflow.

**Target Users:** Non-technical founders, low-code users, first-time builders, and anyone tired of getting broken code from one-shot AI prompts.

---

## 1. Core Components/Directories

| Directory | Purpose | Priority | AI Agent Role |
|-----------|---------|----------|---------------|
| **`/apps`** | Application code (frontend/backend/libs) | 🔴 Core | Development Coordinator |
| **`/docs`** | Technical documentation (API, setup, deployment) | 🔴 Core | Documentation Specialist |
| **`/dev-and-design-guides`** | Planning docs (scope, MVP, SSoT, architecture) | 🔴 Core | Lead Architect, PM |
| **`/tests`** | Test suites (unit, integration, system, acceptance) | 🟡 Important | QA Engineer |
| **`/CI-CD`** | CI/CD pipeline configuration | 🟡 Important | DevOps Specialist |
| **`/packages`** | Shared/publishable packages (for monorepos) | 🟢 Optional | Development Coordinator |
| **`/supabase`** | Database configuration and migrations | 🟢 Optional | Backend Developer |
| **`/dev-tools`** | Development utilities and IDE configs | 🟢 Optional | - |
| **`/logs`** | Development logs and Architecture Decision Records | 🟢 Optional | All agents |
| **`/scripts`** | Build and automation scripts | 🟢 Optional | DevOps Specialist |

---

## 2. File Types You'll Interact With

### Most Frequently
- **`mapfile.md`** - Directory context and work logs (AI agents update these)
- **Markdown templates** - Planning and documentation (`.md` files)
- **`QUICKSTART.md`** - Your starting point
- **`WORKFLOW-GUIDE.md`** - The complete 15-step process

### AI Agents Generate
- **`/dev-and-design-guides/SSOT.md`** - Single Source of Truth (created by Lead Architect)
- **`/docs/*.md`** - Technical specs (created by Documentation Specialist)
- **`/dev-and-design-guides/TASK-LIST.md`** - Development roadmap (created by PM)
- **`/dev-and-design-guides/TESTING-PLAN.md`** - QA strategy (created by QA Engineer)
- **Code in `/apps`** - Features (created by Development Coordinator)

### You Review & Refine
- All AI-generated content needs human review
- Use "Senior Architect" agent to validate AI output
- Provide feedback and request revisions as needed

---

## 3. Pre-configured Tools/Integrations

### Included ✅

**Mapfile System** - Atlas-CLI inspired context management
- Each directory has a `mapfile.md` with YAML frontmatter
- AI agents update work logs automatically
- Tracks ownership, status, dependencies, todos
- See [Atlas-CLI.md](Atlas-CLI.md) for full specification

**Project Map Generator** - `dev-tools/update-root-mapfile.js`
- Aggregates all mapfiles into a single overview
- Provides context for AI agents
- Run after major milestones

**Documentation Templates** - Comprehensive empty templates for:
- API documentation, authentication, deployment, troubleshooting
- Privacy policy, Terms of Service
- Architecture decisions, testing strategies

**Planning Templates** - Structured templates for:
- Brainstorming, scope definition, MVP prioritization
- Build plan, design guide, brand guidelines
- Software requirements specification

**Workflow Documentation** - Complete AI agent orchestration guide:
- [QUICKSTART.md](QUICKSTART.md) - 5-10 minute setup
- [WORKFLOW-GUIDE.md](WORKFLOW-GUIDE.md) - 15-step development process
- [DEVN_NOBLE_SOP.md](.github/instructions/DEVN-NOBLE-SOP.instructions.md) - Quality standards

### NOT Included ❌

**Framework Agnostic by Design:**
- ❌ No specific frontend framework (React/Vue/Svelte)
- ❌ No specific backend framework (Express/Fastify/NestJS)
- ❌ No database ORM or client
- ❌ No testing framework pre-installed
- ❌ No pre-installed dependencies
- ❌ No IDE extensions

**Why?** AI agents will set these up based on your tech stack choices. You choose, agents implement.

---

## 4. Most Important Files to Read First

### 🥇 Start Here: **[QUICKSTART.md](QUICKSTART.md)**

This file explains:
- ✅ How to set up the project (5 minutes)
- ✅ How to brainstorm and scope your app
- ✅ How to use AI agents to generate specs
- ✅ How to get ready for development

**Time Investment:** 10-15 minutes

---

### 🥈 Then Read: **[WORKFLOW-GUIDE.md](WORKFLOW-GUIDE.md)**

The complete 15-step process:
1. **Phase 1:** Architecture & Planning (SSoT creation, spec generation)
2. **Phase 2:** Project Planning (task lists, timelines, testing strategy)
3. **Phase 3:** Development (iterative sprints with AI agents)
4. **Phase 4:** Finalization (marketing, legal, deployment)

**Time Investment:** 15 minutes to understand, 1 day to 1 week to execute

---

### 🥉 Also Important: **[README.md](README.md)**

The project overview:
- Problem this template solves
- What makes it different
- Repo structure
- Devn-Noble standards

---

## Quick Start Checklist

- [ ] Read [QUICKSTART.md](QUICKSTART.md)
- [ ] Clone template and run setup commands
- [ ] Fill in [dev-and-design-guides/brainstorm.md](dev-and-design-guides/brainstorm.md)
- [ ] Use AI agent to generate [dev-and-design-guides/SCOPE.md](dev-and-design-guides/SCOPE.md)
- [ ] Use AI agent to complete [dev-and-design-guides/mvp-mandates.md](dev-and-design-guides/mvp-mandates.md)
- [ ] Follow [WORKFLOW-GUIDE.md](WORKFLOW-GUIDE.md) Step 1: Create SSoT
- [ ] Continue with remaining workflow steps

---

## How This Template Works

### The Core Philosophy

**Documentation-First Development:**
1. You describe what you want to build (brainstorm, scope, MVP)
2. AI agents generate technical specifications from your descriptions
3. AI agents build features following those specifications
4. Tests validate each feature before moving forward
5. You review and refine throughout

**Result:** Production-ready code, not throwaway demos.

### The AI Agent Workflow

**Role-Based Agents:**
- **Lead Architect** - High-level design, creates Single Source of Truth
- **Documentation Specialist** - Generates API docs, setup guides, etc.
- **Project Manager** - Creates task lists and sprint timelines
- **QA Engineer** - Designs testing strategies and writes tests
- **Development Coordinator** - Implements features from specs
- **Senior Architect** - Reviews and validates AI-generated work
- **DevOps Specialist** - Handles deployment configuration

**You orchestrate these agents** following the workflow in WORKFLOW-GUIDE.md.

### The Mapfile System

Every directory has a `mapfile.md` that contains:
- **YAML frontmatter** - Structured metadata (owner, status, dependencies, etc.)
- **Overview** - What this directory is for
- **Work Log** - History of changes (AI agents add entries here)
- **Active Issues** - Current todos
- **Notes** - Additional context

**Purpose:** Give AI agents context about what's already been done and what needs work.

---

## Time Expectations

| Project Type | Planning | Development | Total |
|-------------|----------|-------------|-------|
| Simple CRUD app | 1 hour | 4-8 hours | 1 day |
| Medium complexity | 1.5 hours | 1-2 days | 2-3 days |
| Complex app | 2 hours | 3-5 days | 1 week |

**Note:** These are AI-assisted times. Manual coding would take 3-5x longer.

---

## Need Help?

### Documentation Resources

- **Mapfile format questions?** → See [Atlas-CLI.md](Atlas-CLI.md)
- **Project structure questions?** → See [root-mapfile.md](root-mapfile.md)
- **AI agent prompts?** → See [WORKFLOW-GUIDE.md](WORKFLOW-GUIDE.md)
- **Quality standards?** → See [DEVN_NOBLE_SOP.md](.github/instructions/DEVN-NOBLE-SOP.instructions.md)
- **Development workflow?** → See [dev-and-design-guides/development-guide.md](dev-and-design-guides/development-guide.md)
- **Setup issues?** → See [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md)

### Additional Files

- **[instructions.txt](instructions.txt)** - Additional template details
- **[tips-and-tricks.txt](tips-and-tricks.txt)** - Efficiency tips and AI agent best practices

---

## Philosophy

This template embraces:
- 🤖 **AI-Assisted, Human-Guided** - Agents do the work, you make decisions
- 📝 **Documentation-First** - Write plans before code
- 🗺️ **Context Management** - Mapfiles keep everyone (including AI) aligned
- 🎯 **Quality Over Speed** - Production-ready, not quick hacks
- 🔧 **Framework Agnostic** - Choose your own tools
- 📊 **Trackable Progress** - Work logs create history

**The Goal:** Empower non-technical builders to create production-quality software using AI assistance without sacrificing security, maintainability, or user experience.

---

**Ready to start building?** → Go to [QUICKSTART.md](QUICKSTART.md)
