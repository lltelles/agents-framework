# Project Context

> This file is automatically updated by the `/init` command.
> Last updated: 2025-12-12T16:29:33-03:00

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
| Name | JusAgentic |
| Type | React + TypeScript + Vite Web Application with Express Backend |
| Version | 0.0.0 |
| Last Init | 2025-12-12T16:29:33-03:00 |

## Description

A comprehensive legal platform for Brazilian lawyers featuring AI-powered agents, case management, task tracking with Kanban boards, and document management. Built with a Glassmorphism UI design system using React + TypeScript (Vite) frontend and Express + Prisma (SQL Server) backend.

## Tech Stack

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

## Project Structure

```
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
│   │   ├── controllers/        # Route handlers (4 controllers)
│   │   ├── services/           # Business logic (5 services)
│   │   ├── routes/             # API routes (5 route files)
│   │   ├── middleware/         # Auth & error middleware
│   │   ├── dtos/               # Data Transfer Objects
│   │   ├── config/             # Configuration
│   │   ├── lib/                # Utilities (Prisma client)
│   │   ├── app.ts              # Express app setup
│   │   └── index.ts            # Entry point
│   └── package.json
│
├── src/                        # Frontend Application
│   ├── components/             # React components (31 items)
│   │   ├── landing/           # Landing page (Glassmorphism)
│   │   ├── layout/            # AppLayout, Navigation
│   │   ├── kanban/            # Kanban board components
│   │   ├── agents/            # AI Agent chat UI
│   │   ├── dashboard/         # Dashboard components
│   │   └── ui/                # shadcn/ui primitives
│   ├── pages/                  # Page components (32 items)
│   │   ├── auth/              # Login, Register
│   │   ├── cases/             # Case management pages
│   │   └── dashboard.tsx
│   ├── contexts/               # React contexts (2 items)
│   ├── lib/                    # Utilities
│   ├── router.tsx              # React Router configuration
│   ├── App.tsx                 # Main App component
│   └── index.css               # Global CSS (Tailwind + Glassmorphism)
│
├── shared/                     # Shared types (frontend/backend)
├── tests/                      # E2E tests (Playwright)
├── package.json                # Root package with workspace scripts
└── playwright.config.ts
```

## Core Agents

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
| Phase 4: AI Agents | 🔄 In Progress | 5/7 | ~70% |
| Phase 5: Integration | ⏳ Pending | 0/2 | 0% |
| Phase 6: Testing & Polish | ⏳ Pending | 0/3 | 0% |

### Recent Updates
- Migrated database from PostgreSQL to SQL Server
- Implemented AI agent services with Google Gemini integration
- Built comprehensive case management UI with Kanban boards
- Established Glassmorphism design system

## Active ADRs

| ID | Title | Status | Category |
|----|-------|--------|----------|
| ADR-001 | [Template] | Template | - |

> Use `/adr create "[Title]"` to add Architecture Decision Records.

## Available Scripts

### Frontend (Root)
| Script | Command | Description |
|--------|---------|-------------|
| Development | `npm run dev` | Start Vite dev server with HMR |
| Build | `npm run build` | TypeScript check + production build |
| Lint | `npm run lint` | Run ESLint on codebase |
| Test | `npm run test` | Run Playwright E2E tests |
| Dev All | `npm run dev:all` | Run frontend + backend concurrently |

### Backend (server/)
| Script | Command | Description |
|--------|---------|-------------|
| Development | `npm run dev` | Start Express with tsx watch |
| Build | `npm run build` | Compile TypeScript |
| Database | `npm run db:generate` | Generate Prisma client |
| Migrate | `npm run db:push` | Push schema to database |
| Studio | `npm run db:studio` | Open Prisma Studio |

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

## Environment Configuration

Required environment variables in `server/.env`:
- `DATABASE_URL` - SQL Server connection string
- `JWT_SECRET` - Secret for JWT signing
- `GOOGLE_AI_API_KEY` - Google Gemini API key

## Regenerating This File

Run `/init` to regenerate this file with current project state.
