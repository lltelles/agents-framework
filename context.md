# Project Context

> This file is automatically updated by the `/init` command.
> Last updated: 2025-12-10T21:55:31-03:00

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
| Name | AI-Assisted Development Framework (Agents) |
| Type | AI Framework / Documentation |
| Version | 1.0.0 |
| Last Init | 2025-12-10T21:55:31-03:00 |

## Description

A framework that transforms a single developer into a complete team through specialized AI agents that automate the entire development cycle while following project ADRs (Architecture Decision Records).

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
└── market-research/            # Market Research Module
    ├── agents/                 # Research-specific agents
    ├── docs/                   # Research documentation
    ├── research/               # Research data and findings
    ├── sources/                # Data sources
    ├── context.md             # Research context
    └── README.md              # Research module overview
```

## Key Directories

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

## Active ADRs

| ID | Title | Status | Category |
|----|-------|--------|----------|
| ADR-001 | [Template] | Template | - |

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

## Regenerating This File

Run `/init` to regenerate this file with current project state.

The `/init` command will:
1. Scan the project structure
2. Read package.json for dependencies
3. Identify configuration files
4. Catalog active ADRs
5. Update this context file
