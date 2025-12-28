# Project Context

> This file is automatically updated by the `/init` command.
<<<<<<< HEAD
> Last updated: 2025-12-10T21:55:31-03:00
=======
> Last updated: 2025-12-14T19:10:22-03:00
>>>>>>> 6b0a297b59fcc9bca1bdbf38d70222b3dd40b86d

---

## ⚠️ Important

This file should be regenerated at the start of each session using:

```
/init
```

---

## Project Overview

| Property | Value |
|----------|-------|
<<<<<<< HEAD
| Name | AI-Assisted Development Framework (Agents) |
| Type | AI Framework / Documentation |
| Version | 1.0.0 |
| Last Init | 2025-12-10T21:55:31-03:00 |
=======
| Name | JusAgentic |
| Type | React + TypeScript + Vite Web Application with Express Backend |
| Version | 0.0.0 |
| Last Init | 2025-12-14T19:10:22-03:00 |

## Description

A comprehensive legal platform for Brazilian lawyers featuring AI-powered agents, case management, task tracking with Kanban boards, and document management. Built with a Glassmorphism UI design system using React + TypeScript (Vite) frontend and Express + Prisma (SQL Server) backend.
>>>>>>> 6b0a297b59fcc9bca1bdbf38d70222b3dd40b86d

## Description

<<<<<<< HEAD
A framework that transforms a single developer into a complete team through specialized AI agents that automate the entire development cycle while following project ADRs (Architecture Decision Records).
=======
### Frontend

| Technology | Version | Purpose |
|------------|---------|---------|
| React | 19.2.0 | UI Library |
| TypeScript | 5.9.3 | Type Safety |
| Vite | 7.2.4 | Build Tool & Dev Server |
| Tailwind CSS | 4.1.17 | Utility-First CSS |
| shadcn/ui | - | Component Library |
| @dnd-kit | 6.3.1+ | Drag-and-drop for Kanban |
| Recharts | 3.5.1 | Dashboard Charts |
| React Router | 7.10.1 | Client-side Routing |
| Lucide React | 0.559.0 | Icons |
| Playwright | 1.57.0 | E2E Testing |

### Backend

| Technology | Version | Purpose |
|------------|---------|---------|
| Express | 4.21.0 | HTTP Server |
| TypeScript | 5.7.2 | Type Safety |
| Prisma | 6.8.0 | ORM & Database Client |
| SQL Server | - | Database |
| @langchain/google-genai | 0.1.0 | AI Agent Framework |
| @google/generative-ai | 0.24.1 | Google Gemini API |
| bcrypt | 6.0.0 | Password Hashing |
| jsonwebtoken | 9.0.3 | JWT Authentication |
| Zod | 3.25.76 | Validation |
| Helmet | 8.0.0 | Security Headers |
>>>>>>> 6b0a297b59fcc9bca1bdbf38d70222b3dd40b86d

## Project Structure

```
<<<<<<< HEAD
agents/
├── .ai/                        # AI-Assisted Development Framework
│   ├── agents/                 # Agent prompt templates
│   │   ├── PLAN.md            # Planning Agent (Business Analyst)
│   │   ├── TASKS.md           # Task Decomposition Agent (Tech Lead)
│   │   ├── DEV.md             # Development Agent (Specialized Developer)
│   │   ├── REV.md             # Review Agent (Code Reviewer)
│   │   └── templates/         # Templates for custom agents
│   ├── adr/                    # Architecture Decision Records
│   │   ├── index.md           # ADR registry
│   │   └── template.md        # ADR template
│   ├── docs/                   # Framework documentation
│   ├── prd/                    # Product Requirements Documents
│   │   └── template.md        # PRD template
│   ├── tasks/                  # Generated task files
│   ├── context.md             # This file (project context)
│   └── README.md              # Framework overview
│
└── market-research/            # Market Research Module
    ├── agents/                 # Research-specific agents
    ├── docs/                   # Research documentation
    ├── research/               # Research data and findings
    ├── sources/                # Data sources
    ├── context.md             # Research context
    └── README.md              # Research module overview
=======
jusagentic/
├── .ai/                        # AI-Assisted Development Framework
│   ├── agents/                 # Agent prompt templates (PLAN, TASKS, DEV, REV)
│   ├── adr/                    # Architecture Decision Records
│   ├── docs/                   # Framework documentation
│   ├── prd/                    # Product Requirements Documents
│   │   └── PRD-001-jusagentic-legal-platform.md
│   ├── tasks/                  # Generated task files
│   │   └── PRD-001-task-board.md (28 tasks, 6 phases)
│   └── context.md              # This file
│
├── server/                     # Backend Application
│   ├── prisma/                 # Database schema & migrations
│   │   └── schema.prisma
│   ├── src/
│   │   ├── controllers/        # Route handlers (6 controllers)
│   │   ├── services/           # Business logic (7 services)
│   │   ├── routes/             # API routes (7 route files)
│   │   ├── middleware/         # Auth & error middleware
│   │   ├── dtos/               # Data Transfer Objects (8 DTOs)
│   │   ├── config/             # Configuration
│   │   ├── lib/                # Utilities (Prisma client)
│   │   ├── app.ts              # Express app setup
│   │   └── index.ts            # Entry point
│   └── package.json
│
├── src/                        # Frontend Application
│   ├── business/               # Business logic layer (DTOs & Services)
│   │   ├── dto/                # Request/Response DTOs (5 items)
│   │   └── service/            # Frontend API services (4 items)
│   ├── components/             # React components (38 items)
│   │   ├── landing/            # Landing page (Glassmorphism, 8 items)
│   │   ├── layout/             # AppLayout, Navigation (4 items)
│   │   ├── agents/             # AI Agent chat UI (1 item)
│   │   ├── auth/               # Authentication forms (2 items)
│   │   └── ui/                 # shadcn/ui primitives (21 items)
│   ├── pages/                  # Page components (54 items)
│   │   ├── auth/               # Login, Register (8 items)
│   │   ├── cases/              # Case management pages (33 items)
│   │   ├── agents/             # AI Agent pages (4 items)
│   │   ├── dashboard/          # Dashboard components (4 items)
│   │   └── kanban/             # Kanban board (4 items)
│   ├── contexts/               # React contexts (2 items)
│   ├── lib/                    # Utilities (2 items)
│   ├── router.tsx              # React Router configuration
│   ├── App.tsx                 # Main App component
│   └── index.css               # Global CSS (Tailwind + Glassmorphism)
│
├── shared/                     # Shared types (frontend/backend)
├── tests/                      # E2E tests (Playwright)
├── package.json                # Root package with workspace scripts
└── playwright.config.ts
>>>>>>> 6b0a297b59fcc9bca1bdbf38d70222b3dd40b86d
```

## Core Agents

<<<<<<< HEAD
| Directory | Purpose |
|-----------|---------|
| `.ai/agents/` | Core agent prompt templates (PLAN, TASKS, DEV, REV) |
| `.ai/adr/` | Architecture Decision Records |
| `.ai/docs/` | Framework documentation |
| `.ai/prd/` | PRD templates |
| `.ai/tasks/` | Generated task breakdowns |
| `market-research/` | Independent market research module |

## Core Agents

| Agent | Role Equivalent | Purpose |
|-------|-----------------|---------|
| **PLAN** | Business Analyst / Solution Architect | Creates comprehensive PRDs from user stories |
| **TASKS** | Tech Lead | Decomposes PRDs into prioritized technical tasks |
| **DEV** | Specialized Developer | Implements code, tests, and documentation |
| **REV** | Code Reviewer / Security Analyst | Reviews implementation for quality and compliance |
=======
| Agent | Role Equivalent | Purpose |
|-------|-----------------|---------|
| **PLAN** | Business Analyst | Creates comprehensive PRDs from user stories |
| **TASKS** | Tech Lead | Decomposes PRDs into prioritized technical tasks |
| **DEV** | Developer | Implements code, tests, and documentation |
| **REV** | Reviewer | Reviews implementation for quality and compliance |

## AI Agent System (Legal Specialists)

| Agent | Portuguese Name | Purpose |
|-------|-----------------|---------|
| ESTRATÉGIA | Estratégia | Creates comprehensive case plans |
| TAREFAS | Tarefas | Generates and manages task lists |
| PESQUISA | Pesquisa | Legal research and jurisprudence |
| REDAÇÃO | Redação | Document drafting |
| REVISÃO | Revisão | Review and quality check |

## Development Progress

### Phase Status

| Phase | Status | Tasks | Progress |
|-------|--------|-------|----------|
| Phase 1: Foundation | ✅ Complete | 5/5 | 100% |
| Phase 2: Core UI | ✅ Complete | 7/7 | 100% |
| Phase 3: Backend Services | ✅ Complete | 4/4 | 100% |
| Phase 4: AI Agents | ✅ Complete | 7/7 | 100% |
| Phase 5: Integration | ✅ Complete | 2/2 | 100% |
| Phase 6: Testing & Polish | 🔄 In Progress | 1/3 | ~33% |

### Recent Updates
- Implemented document management with blob URL previews
- Fixed case detail type error for proper data display
- Moved document utility functions to `documents.model.ts` for better organization
- Migrated database from PostgreSQL to SQL Server
- Implemented AI agent services with Google Gemini integration
- Built comprehensive case management UI with Kanban boards
- Established Glassmorphism design system
- Integrated frontend with backend API services

### Backend Services

| Service | File | Description |
|---------|------|-------------|
| Auth | `auth.service.ts` | JWT authentication with bcrypt |
| Cases | `cases.service.ts` | Case CRUD with pinning support |
| Tasks | `tasks.service.ts` | Task management for Kanban |
| Documents | `documents.service.ts` | Document storage and retrieval |
| Dashboard | `dashboard.service.ts` | Statistics and metrics |
| Agents | `agents.service.ts` | AI agent orchestration |
| Gemini | `gemini.service.ts` | Google Gemini API integration |

### Frontend Business Layer

| Component | Directory | Description |
|-----------|-----------|-------------|
| DTOs | `src/business/dto/` | 5 Data Transfer Objects |
| Services | `src/business/service/` | 4 API service clients |
>>>>>>> 6b0a297b59fcc9bca1bdbf38d70222b3dd40b86d

## Active ADRs

| ID | Title | Status | Category |
|----|-------|--------|----------|
| ADR-001 | [Template] | Template | - |

<<<<<<< HEAD
> No active ADRs have been created yet. Use `/adr create "[Title]"` to add ADRs.

## Essential Commands

| Command | Description |
|---------|-------------|
| `/init` | Updates application context to prevent hallucinations |
| `/clear` | Clears context between tasks for predictability |
| `/agents` | Lists, creates, or updates agents |
| `/status` | Shows current workflow status |
| `/adr` | Lists or creates Architecture Decision Records |

## Workflow

```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│   PLAN   │───▶│  TASKS   │───▶│   DEV    │───▶│   REV    │
│          │    │          │    │          │    │          │
│ PRD +    │    │ Task     │    │ Code +   │    │ Quality  │
│ ADR Refs │    │ Breakdown│    │ Tests    │    │ Check    │
└──────────┘    └──────────┘    └──────────┘    └──────────┘
      │                              │               │
      ▼                              ▼               ▼
┌─────────────────────────────────────────────────────────┐
│                   ADR Repository                         │
│  (Architecture, Security, Patterns, Standards)          │
└─────────────────────────────────────────────────────────┘
```

## Current State

### Active Development
- Framework is fully initialized and ready for use
- Market Research module contains active research on potential opportunities

### Available Modules
- **AI Framework** (`.ai/`) - Core agent-based development workflow
- **Market Research** (`market-research/`) - Problem discovery and opportunity validation

### Known Issues
- No known issues at this time

## Notes

This is a meta-framework project - it contains the AI-assisted development framework itself rather than a traditional application. The agents defined here can be used to develop any React + TypeScript or Node.js project.

To use this framework in another project, copy the `.ai` folder to your project root and run `/init`.

---
=======
> Use `/adr create "[Title]"` to add Architecture Decision Records.

## Available Scripts

### Frontend (Root)
| Script | Command | Description |
|--------|---------|-------------|
| Development | `npm run dev` | Start Vite dev server with HMR |
| Build | `npm run build` | TypeScript check + production build |
| Lint | `npm run lint` | Run ESLint on codebase |
| Test | `npm run test` | Run Playwright E2E tests |
| Test UI | `npm run test:ui` | Run Playwright with UI |
| Test Headed | `npm run test:headed` | Run Playwright headed |
| Dev All | `npm run dev:all` | Run frontend + backend concurrently |

### Backend (server/)
| Script | Command | Description |
|--------|---------|-------------|
| Development | `npm run dev` | Start Express with tsx watch |
| Build | `npm run build` | Compile TypeScript |
| Database | `npm run db:generate` | Generate Prisma client |
| Migrate | `npm run db:push` | Push schema to database |
| Studio | `npm run db:studio` | Open Prisma Studio |
| Seed | `npm run db:seed` | Seed database with sample data |

## Essential Commands

| Command | Description |
|---------|-------------|
| `/init` | Updates application context to prevent hallucinations |
| `/clear` | Clears context between tasks for predictability |
| `/agents` | Lists, creates, or updates agents |
| `/status` | Shows current workflow status |
| `/adr` | Lists or creates Architecture Decision Records |

## Implementation Notes

- **UI System**: Custom Glassmorphism design with `.glass` and `.glass-heavy` utility classes in `index.css`
- **Dark Mode**: Enforced by default for glass design compatibility
- **Database**: SQL Server (migrated from PostgreSQL)
- **AI Provider**: Google Gemini via LangChain (requires `GOOGLE_AI_API_KEY` in `.env`)
- **Auth**: JWT-based with bcrypt password hashing
- **Architecture**: Clean separation with business layer (DTOs + Services) in frontend

## Environment Configuration

Required environment variables in `server/.env`:
- `DATABASE_URL` - SQL Server connection string
- `JWT_SECRET` - Secret for JWT signing
- `GOOGLE_AI_API_KEY` - Google Gemini API key
>>>>>>> 6b0a297b59fcc9bca1bdbf38d70222b3dd40b86d

## Regenerating This File

Run `/init` to regenerate this file with current project state.
