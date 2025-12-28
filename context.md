---
modified: 2025-12-28T01:12:48.891Z
title: Project Context
---

# Project Context

> This file is automatically updated by the `/init` command.
> Last updated: 2025-12-27T22:04:36-03:00

---

## ⚠️ Important

This file should be regenerated at the start of each session using:

```
/init
```

---

## Project Overview

| Property  | Value                                                          |
| --------- | -------------------------------------------------------------- |
| Name      | JusAgentic                                                     |
| Type      | React + TypeScript + Vite Web Application with Express Backend |
| Version   | 0.0.0                                                          |
| Last Init | 2025-12-27T22:04:36-03:00                                      |

## Description

A comprehensive legal platform for Brazilian lawyers featuring AI-powered agents, case management, task tracking with Kanban boards, document management, and a rich text editor. Built with a Glassmorphism UI design system using React + TypeScript (Vite) frontend and Express + Prisma (SQL Server) backend.

## Tech Stack

### Frontend

| Technology         | Version  | Purpose                  |
| ------------------ | -------- | ------------------------ |
| React              | 19.2.0   | UI Library               |
| TypeScript         | 5.9.3    | Type Safety              |
| Vite               | 7.2.4    | Build Tool & Dev Server  |
| Tailwind CSS       | 4.1.17   | Utility-First CSS        |
| shadcn/ui          | -        | Component Library        |
| @dnd-kit           | 6.3.1+   | Drag-and-drop for Kanban |
| Recharts           | 3.5.1    | Dashboard Charts         |
| React Router       | 7.10.1   | Client-side Routing      |
| Lucide React       | 0.559.0  | Icons                    |
| Framer Motion      | 12.23.26 | Animations               |
| TipTap             | 3.14.0   | Rich Text Editor         |
| Playwright         | 1.57.0   | E2E Testing              |
| react-helmet-async | 2.0.5    | SEO Meta Tags            |

### Backend

| Technology              | Version | Purpose                 |
| ----------------------- | ------- | ----------------------- |
| Express                 | 4.21.0  | HTTP Server             |
| TypeScript              | 5.7.2   | Type Safety             |
| Prisma                  | 6.8.0   | ORM & Database Client   |
| SQL Server              | -       | Database                |
| @langchain/google-genai | 0.1.0   | AI Agent Framework      |
| @google/generative-ai   | 0.24.1  | Google Gemini API       |
| LlamaIndex              | 0.12.1  | Document Indexing & RAG |
| bcrypt                  | 6.0.0   | Password Hashing        |
| jsonwebtoken            | 9.0.3   | JWT Authentication      |
| Zod                     | 3.25.76 | Validation              |
| Helmet                  | 8.0.0   | Security Headers        |
| Resend                  | 6.6.0   | Email Service           |
| Puppeteer               | 24.34.0 | PDF Generation          |
| Tesseract.js            | 7.0.0   | OCR for Image Documents |

## Project Structure

```
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
├── server/                     # Backend Application
│   ├── prisma/                 # Database schema & migrations
│   │   └── schema.prisma
│   ├── src/
│   │   ├── controllers/        # Route handlers (7 controllers)
│   │   ├── services/           # Business logic (14 services)
│   │   ├── routes/             # API routes (8 route files)
│   │   ├── middleware/         # Auth & error middleware (3 files)
│   │   ├── dtos/               # Data Transfer Objects (9 DTOs)
│   │   ├── config/             # Configuration
│   │   ├── lib/                # Utilities (Prisma client)
│   │   ├── app.ts              # Express app setup
│   │   └── index.ts            # Entry point
│   └── package.json
│
├── src/                        # Frontend Application
│   ├── business/               # Business logic layer (DTOs & Services)
│   │   ├── dto/                # Request/Response DTOs
│   │   └── service/            # Frontend API services
│   ├── components/             # React components (42 items)
│   │   ├── landing/            # Landing page (Glassmorphism)
│   │   ├── layout/             # AppLayout, Navigation
│   │   ├── agents/             # AI Agent chat UI
│   │   ├── auth/               # Authentication forms
│   │   ├── seo/                # SEO component
│   │   └── ui/                 # shadcn/ui primitives
│   ├── pages/                  # Page components (96 items)
│   │   ├── auth/               # Login, Register, Password Reset (16 items)
│   │   ├── cases/              # Case management pages (36 items)
│   │   ├── agents/             # AI Agent pages (19 items)
│   │   ├── dashboard/          # Dashboard components (5 items)
│   │   ├── kanban/             # Kanban board (4 items)
│   │   ├── editor/             # Rich text editor (7 items)
│   │   ├── profile/            # User profile (4 items)
│   │   └── error/              # Error pages (4 items)
│   ├── contexts/               # React contexts (2 items)
│   ├── lib/                    # Utilities (5 items)
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

| Agent     | Role Equivalent  | Purpose                                           |
| --------- | ---------------- | ------------------------------------------------- |
| **PLAN**  | Business Analyst | Creates comprehensive PRDs from user stories      |
| **TASKS** | Tech Lead        | Decomposes PRDs into prioritized technical tasks  |
| **DEV**   | Developer        | Implements code, tests, and documentation         |
| **REV**   | Reviewer         | Reviews implementation for quality and compliance |

## Core Agents

| Agent      | Portuguese Name | Purpose                          |
| ---------- | --------------- | -------------------------------- |
| ESTRATÉGIA | Estratégia      | Creates comprehensive case plans |
| TAREFAS    | Tarefas         | Generates and manages task lists |
| PESQUISA   | Pesquisa        | Legal research and jurisprudence |
| REDAÇÃO    | Redação         | Document drafting                |
| REVISÃO    | Revisão         | Review and quality check         |

## Development Progress

### Phase Status

| Phase                     | Status         | Tasks | Progress |
| ------------------------- | -------------- | ----- | -------- |
| Phase 1: Foundation       | ✅ Complete    | 5/5   | 100%     |
| Phase 2: Core UI          | ✅ Complete    | 7/7   | 100%     |
| Phase 3: Backend Services | ✅ Complete    | 4/4   | 100%     |
| Phase 4: AI Agents        | ✅ Complete    | 7/7   | 100%     |
| Phase 5: Integration      | ✅ Complete    | 2/2   | 100%     |
| Phase 6: Testing & Polish | 🔄 In Progress | 2/3   | ~66%     |

### Recent Updates (December 2025)

- Implemented password reset flow with email templates (dark mode branding)
- Added PDF export functionality with `html2pdf.js`
- Implemented document content extraction using Gemini Vision API
- Added agent context files for multimodal analysis
- Implemented rich text editor integration with Redator/Revisor agents
- Centralized priority configuration across components
- Implemented SEO with react-helmet-async for all pages
- Added inline case description editing
- Optimized caching for dashboard and agent conversations
- Removed legacy multi-agent workflow mode

### Backend Services

| Service             | File                             | Description                                    |
| ------------------- | -------------------------------- | ---------------------------------------------- |
| Auth                | `auth.service.ts`                | JWT authentication with bcrypt, password reset |
| Cases               | `cases.service.ts`               | Case CRUD with pinning support                 |
| Tasks               | `tasks.service.ts`               | Task management for Kanban                     |
| Documents           | `documents.service.ts`           | Document storage and retrieval                 |
| Document Extraction | `document-extraction.service.ts` | OCR and Gemini Vision for content extraction   |
| Document Chunking   | `document-chunking.service.ts`   | Text chunking for RAG                          |
| Dashboard           | `dashboard.service.ts`           | Statistics and metrics                         |
| Agents              | `agents.service.ts`              | AI agent orchestration                         |
| Agent Conversations | `agent-conversations.service.ts` | Conversation history management                |
| Gemini              | `gemini.service.ts`              | Google Gemini API integration                  |
| Email               | `email.service.ts`               | Transactional emails via Resend                |
| PDF                 | `pdf.service.ts`                 | PDF generation with Puppeteer                  |
| Embedding           | `embedding.service.ts`           | Vector embeddings for search                   |
| Vector Search       | `vector-search.service.ts`       | Semantic document search                       |

### Frontend Business Layer

| Component | Directory               | Description           |
| --------- | ----------------------- | --------------------- |
| DTOs      | `src/business/dto/`     | Data Transfer Objects |
| Services  | `src/business/service/` | API service clients   |

## Active ADRs

| ID      | Title      | Status   | Category |
| ------- | ---------- | -------- | -------- |
| ADR-001 | [Template] | Template | -        |

> Use `/adr create "[Title]"` to add Architecture Decision Records.

## Available Scripts

### Frontend (Root)

| Script      | Command               | Description                         |
| ----------- | --------------------- | ----------------------------------- |
| Development | `npm run dev`         | Start Vite dev server with HMR      |
| Build       | `npm run build`       | TypeScript check + production build |
| Lint        | `npm run lint`        | Run ESLint on codebase              |
| Test        | `npm run test`        | Run Playwright E2E tests            |
| Test UI     | `npm run test:ui`     | Run Playwright with UI              |
| Test Headed | `npm run test:headed` | Run Playwright headed               |
| Dev All     | `npm run dev:all`     | Run frontend + backend concurrently |

### Backend (server/)

| Script      | Command               | Description                    |
| ----------- | --------------------- | ------------------------------ |
| Development | `npm run dev`         | Start Express with tsx watch   |
| Build       | `npm run build`       | Compile TypeScript             |
| Database    | `npm run db:generate` | Generate Prisma client         |
| Migrate     | `npm run db:push`     | Push schema to database        |
| Studio      | `npm run db:studio`   | Open Prisma Studio             |
| Seed        | `npm run db:seed`     | Seed database with sample data |

## Essential Commands

| Command   | Description                                           |
| --------- | ----------------------------------------------------- |
| `/init`   | Updates application context to prevent hallucinations |
| `/clear`  | Clears context between tasks for predictability       |
| `/agents` | Lists, creates, or updates agents                     |
| `/status` | Shows current workflow status                         |
| `/adr`    | Lists or creates Architecture Decision Records        |

## Workflow

- **UI System**: Custom Glassmorphism design with `.glass` and `.glass-heavy` utility classes in `index.css`
- **Dark Mode**: Enforced by default for glass design compatibility
- **Database**: SQL Server (migrated from PostgreSQL)
- **AI Provider**: Google Gemini via LangChain (requires `GOOGLE_AI_API_KEY` in `.env`)
- **Document Processing**: Gemini Vision API for OCR and content extraction
- **Auth**: JWT-based with bcrypt password hashing, password reset via email
- **Architecture**: Clean separation with business layer (DTOs + Services) in frontend
- **Caching**: Client-side caching for dashboard stats and agent conversations (1 hour TTL)

## Current State

Required environment variables in `server/.env`:

- `DATABASE_URL` - SQL Server connection string
- `JWT_SECRET` - Secret for JWT signing
- `GOOGLE_AI_API_KEY` - Google Gemini API key
- `RESEND_API_KEY` - Resend API key for emails
- `APP_URL` - Frontend application URL

## Regenerating This File

Run `/init` to regenerate this file with current project state.
