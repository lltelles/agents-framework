# Project Context

> This file is automatically updated by the `/init` command.
> Last updated: 2025-12-11T15:22:03-03:00

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
| Type | React + TypeScript + Vite Web Application |
| Version | 0.0.0 |
| Last Init | 2025-12-11T15:22:03-03:00 |

## Description

A React + TypeScript web application built with Vite, featuring Tailwind CSS v4 for styling and shadcn/ui component library integration. 
**Recent Updates**: Integrated a comprehensive Glassmorphism UI design system with mesh gradients, translucent panels, and modern micro-interactions, particularly on the Landing Page.

## Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| React | 19.2.0 | UI Library |
| TypeScript | 5.9.3 | Type Safety |
| Vite | 7.2.4 | Build Tool & Dev Server |
| Tailwind CSS | 4.1.17 | Utility-First CSS |
| shadcn/ui | - | Component Library (configured) |
| ESLint | 9.39.1 | Code Linting |

## Project Structure

```
jusagentic/
├── .ai/                        # AI-Assisted Development Framework
│   ├── agents/                 # Agent prompt templates
│   │   ├── PLAN.md            # Planning Agent
│   │   ├── TASKS.md           # Task Decomposition Agent
│   │   ├── DEV.md             # Development Agent
│   │   └── REV.md             # Review Agent
│   ├── adr/                    # Architecture Decision Records
│   ├── docs/                   # Framework documentation
│   ├── prd/                    # Product Requirements Documents
│   ├── tasks/                  # Generated task files
│   ├── context.md             # This file (project context)
│   └── README.md              # Framework overview
│
├── public/                     # Static assets
├── src/                        # Source code
│   ├── assets/                # Application assets
│   ├── components/            # React components
│   │   ├── landing/           # Landing page specific components (Glassmorphism)
│   │   ├── layout/            # Layout components (AppLayout)
│   │   ├── ui/                # shadcn/ui primitives (Button, etc.)
│   │   ├── theme-provider.tsx # Theme context provider
│   │   └── theme-toggle.tsx   # Dark mode toggle
│   ├── lib/                   # Utility libraries
│   │   └── utils.ts           # Helper functions
│   ├── pages/                 # Page components (Routed)
│   │   ├── auth/              # Authentication pages (Login)
│   │   ├── cases/             # Case management pages
│   │   ├── dashboard.tsx      # Dashboard page
│   │   └── landing.tsx        # Landing page (Glassmorphism)
│   ├── router.tsx             # React Router configuration
│   ├── App.tsx                # Main App component (Template)
│   ├── index.css              # Global CSS (Tailwind + Glassmorphism styles)
│   └── main.tsx               # Application entry point
│
├── components.json            # shadcn/ui configuration
├── eslint.config.js           # ESLint configuration
├── index.html                 # HTML entry point
├── package.json               # Dependencies and scripts
├── tsconfig.json              # TypeScript configuration
├── vite.config.ts             # Vite configuration
└── ...
```

## Key Directories

| Directory | Purpose |
|-----------|---------|
| `src/components/landing/` | Glassmorphism components for the landing page |
| `src/components/ui/` | Reusable UI primitives (shadcn/ui) |
| `.ai/` | AI-Assisted Development Framework metadata |

## Core Agents

| Agent | Role Equivalent | Purpose |
|-------|-----------------|---------|
| **PLAN** | Business Analyst | Creates comprehensive PRDs from user stories |
| **TASKS** | Tech Lead | Decomposes PRDs into prioritized technical tasks |
| **DEV** | Developer | Implements code, tests, and documentation |
| **REV** | Reviewer | Reviews implementation for quality and compliance |

## Active ADRs

| ID | Title | Status | Category |
|----|-------|--------|----------|
| ADR-001 | [Template] | Template | - |

> No active ADRs have been created yet. Use `/adr create "[Title]"` to add ADRs.

## Available Scripts

| Script | Command | Description |
|--------|---------|-------------|
| Development | `npm run dev` | Start Vite dev server with HMR |
| Build | `npm run build` | TypeScript check + production build |
| Lint | `npm run lint` | Run ESLint on codebase |
| Preview | `npm run preview` | Preview production build |

## Essential Commands

| Command | Description |
|---------|-------------|
| `/init` | Updates application context to prevent hallucinations |
| `/clear` | Clears context between tasks for predictability |
| `/agents` | Lists, creates, or updates agents |
| `/status` | Shows current workflow status |
| `/adr` | Lists or creates Architecture Decision Records |

## Implementation Notes
- **UI System**: The project uses a custom Glassmorphism design over Shadcn UI. Key utility classes like `.glass` and `.glass-heavy` are defined in `index.css`.
- **Dark Mode**: The application enforces dark mode by default (`document.documentElement.classList.add('dark')` in `main.tsx`) to support the glass design.

## Regenerating This File

Run `/init` to regenerate this file with current project state.
