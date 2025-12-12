# Task Board: JusAgentic Legal Platform

> **PRD Reference**: PRD-001-jusagentic-legal-platform
> **Created**: 2025-12-10
> **Author**: Agent TASKS
> **Status**: Ready for Execution

---

## Summary

- **Total Tasks**: 28
- **Estimated Effort**: ~120 hours
- **Critical Path**: TASK-001 → TASK-002 → TASK-004 → TASK-008 → TASK-014 → TASK-019 → TASK-024

## Dependency Graph

```
Phase 1: Foundation
  TASK-001 (Project Setup)
       │
       ├──► TASK-002 (Design System)
       │         │
       │         └──► TASK-003 (Core UI Components)
       │
       └──► TASK-004 (Database Schema)
                 │
                 └──► TASK-005 (Backend API Setup)

Phase 2: Core UI
  TASK-003 ──► TASK-006 (Auth UI)
          ──► TASK-007 (Layout)
          ──► TASK-008 (Dashboard)
          ──► TASK-009 (Case List)
          ──► TASK-010 (Case Form)
          ──► TASK-011 (Case Detail)
          ──► TASK-012 (Kanban Board)

Phase 3: Backend Services
  TASK-005 ──► TASK-013 (Auth Service)
          ──► TASK-014 (Case Service)
          ──► TASK-015 (Task Service)
          ──► TASK-016 (Document Service)

Phase 4: AI Agents
  TASK-014/015 ──► TASK-017 (Agent Orchestrator)
               ──► TASK-018 (ESTRATÉGIA Agent)
               ──► TASK-019 (TAREFAS Agent)
               ──► TASK-020 (PESQUISA Agent)
               ──► TASK-021 (REDAÇÃO Agent)
               ──► TASK-022 (REVISÃO Agent)
               ──► TASK-023 (Agent UI Panel)

Phase 5: Integration
  All UI + Backend ──► TASK-024 (Frontend-Backend Integration)
                   ──► TASK-025 (WebSocket Streaming)

Phase 6: Testing & Polish
  TASK-024/025 ──► TASK-026 (E2E Tests)
               ──► TASK-027 (LGPD Compliance)
               ──► TASK-028 (Documentation)
```

---

## Execution Order

### Phase 1: Foundation (Week 1)

| ID | Title | Priority | Complexity | Type | Dependencies |
|----|-------|----------|------------|------|--------------|
| TASK-001 | Project Structure Setup | Critical | M (3h) | Setup | None |
| TASK-002 | Design System & Dark Mode | Critical | M (4h) | Feature | TASK-001 |
| TASK-003 | Core shadcn/ui Components | Critical | L (6h) | Feature | TASK-002 |
| TASK-004 | Database Schema (Prisma) | Critical | L (4h) | Feature | TASK-001 |
| TASK-005 | Backend API Setup (Express) | Critical | M (4h) | Feature | TASK-004 |

**Phase 1 Total**: ~21 hours

---

### Phase 2: Core UI (Week 2-3)

| ID | Title | Priority | Complexity | Type | Dependencies |
|----|-------|----------|------------|------|--------------|
| TASK-006 | Authentication UI | Critical | M (4h) | Feature | TASK-003 |
| TASK-007 | App Layout & Navigation | Critical | M (3h) | Feature | TASK-003 |
| TASK-008 | Dashboard Page | High | L (6h) | Feature | TASK-007 |
| TASK-009 | Case List Page | High | M (4h) | Feature | TASK-007 |
| TASK-010 | Case Creation Form | High | M (4h) | Feature | TASK-003 |
| TASK-011 | Case Detail Page | High | L (6h) | Feature | TASK-007 |
| TASK-012 | Kanban Board Component | Critical | XL (10h) | Feature | TASK-011 |

**Phase 2 Total**: ~37 hours

---

### Phase 3: Backend Services (Week 2-3)

| ID | Title | Priority | Complexity | Type | Dependencies |
|----|-------|----------|------------|------|--------------|
| TASK-013 | Authentication Service | Critical | M (4h) | Feature | TASK-005 |
| TASK-014 | Case CRUD Service | Critical | M (4h) | Feature | TASK-005 |
| TASK-015 | Task CRUD Service | High | M (4h) | Feature | TASK-005 |
| TASK-016 | Document Storage Service | Medium | M (3h) | Feature | TASK-005 |

**Phase 3 Total**: ~15 hours

---

### Phase 4: AI Agents (Week 4-5)

| ID | Title | Priority | Complexity | Type | Dependencies |
|----|-------|----------|------------|------|--------------|
| TASK-017 | Agent Orchestrator (LangChain) | Critical | L (6h) | Feature | TASK-005 |
| TASK-018 | ESTRATÉGIA Agent | Critical | L (6h) | Feature | TASK-017 |
| TASK-019 | TAREFAS Agent | High | M (4h) | Feature | TASK-017 |
| TASK-020 | PESQUISA Agent | High | L (6h) | Feature | TASK-017 |
| TASK-021 | REDAÇÃO Agent | High | L (6h) | Feature | TASK-017 |
| TASK-022 | REVISÃO Agent | Medium | M (4h) | Feature | TASK-017 |
| TASK-023 | Agent Chat UI Panel | High | L (6h) | Feature | TASK-003, TASK-017 |

**Phase 4 Total**: ~38 hours

---

### Phase 5: Integration (Week 5-6)

| ID | Title | Priority | Complexity | Type | Dependencies |
|----|-------|----------|------------|------|--------------|
| TASK-024 | Frontend-Backend Integration | Critical | L (6h) | Integration | TASK-008-012, TASK-013-016 |
| TASK-025 | WebSocket Streaming for Agents | High | M (4h) | Feature | TASK-023, TASK-017 |

**Phase 5 Total**: ~10 hours

---

### Phase 6: Testing & Polish (Week 6-7)

| ID | Title | Priority | Complexity | Type | Dependencies |
|----|-------|----------|------------|------|--------------|
| TASK-026 | E2E Tests (Playwright) | High | L (6h) | Test | TASK-024 |
| TASK-027 | LGPD Compliance Implementation | Critical | M (4h) | Feature | TASK-024 |
| TASK-028 | Documentation & README | Medium | S (2h) | Documentation | TASK-024 |

**Phase 6 Total**: ~12 hours

---

## Individual Task Details

### TASK-001: Project Structure Setup

**PRD Reference**: Technical Specifications - Technology Stack
**Priority**: Critical | **Complexity**: M (3h) | **Type**: Setup | **Spec**: Full-stack

#### Description
Set up the monorepo or project structure with frontend (existing Vite) and backend (new Express/Node.js) directories. Configure TypeScript, ESLint, and shared types.

#### Acceptance Criteria
- [ ] Backend folder created with Express/Fastify setup
- [ ] Shared types directory for frontend/backend
- [ ] Environment configuration (.env files)
- [ ] ESLint and Prettier configured for both
- [ ] Scripts for running dev servers

#### Technical Approach
1. Create `server/` directory for backend
2. Initialize with `npm init` and TypeScript
3. Create `shared/` directory for types
4. Update root package.json with workspace scripts
5. Configure path aliases

#### Files to Create/Modify
- `server/package.json` - Backend dependencies
- `server/tsconfig.json` - Backend TS config
- `server/src/index.ts` - Entry point
- `shared/types/` - Shared TypeScript types
- `package.json` - Workspace scripts

#### Dependencies
- **Blocked by**: None
- **Blocks**: TASK-002, TASK-004

---

### TASK-002: Design System & Dark Mode

**PRD Reference**: UI/UX Specifications - Design System, FR-012
**Priority**: Critical | **Complexity**: M (4h) | **Type**: Feature | **Spec**: Frontend

#### Description
Establish the design system with dark mode as default, color palette, typography, and CSS variables. Configure Tailwind for legal-themed dark mode.

#### Acceptance Criteria
- [ ] Dark mode enabled by default
- [ ] Light mode toggle functional
- [ ] Color palette defined (indigo primary, emerald accents)
- [ ] Typography system (Inter font)
- [ ] CSS variables for theme colors
- [ ] Proper contrast ratios (>4.5:1)

#### Technical Approach
1. Update `index.css` with CSS variables for dark/light themes
2. Configure Tailwind config for custom colors
3. Create ThemeProvider context
4. Add theme toggle component
5. Test accessibility contrast

#### Files to Create/Modify
- `src/index.css` - CSS variables, dark mode base
- `src/lib/theme.ts` - Theme utilities
- `src/components/theme-provider.tsx` - Theme context
- `src/components/theme-toggle.tsx` - Toggle button

#### Dependencies
- **Blocked by**: TASK-001
- **Blocks**: TASK-003

---

### TASK-003: Core shadcn/ui Components

**PRD Reference**: Technical Specifications - UI Components
**Priority**: Critical | **Complexity**: L (6h) | **Type**: Feature | **Spec**: Frontend

#### Description
Install and configure essential shadcn/ui components needed across the application: Button, Card, Input, Dialog, Sheet, Dropdown, Table, Tabs, Toast, and more.

#### Acceptance Criteria
- [ ] All required shadcn/ui components installed
- [ ] Components styled for dark mode
- [ ] Lucide icons integrated
- [ ] Component variants created if needed

#### Technical Approach
1. Use `npx shadcn@latest add [component]` for each
2. Customize component themes
3. Create any composite components

#### Required Components
```
button, card, input, label, textarea, select
dialog, sheet, dropdown-menu, popover
table, tabs, badge, avatar
toast, alert, skeleton
form (react-hook-form integration)
```

#### Files to Create
- `src/components/ui/*.tsx` - Individual components

#### Dependencies
- **Blocked by**: TASK-002
- **Blocks**: TASK-006, TASK-007, TASK-008, TASK-009, TASK-010, TASK-011, TASK-012, TASK-023

---

### TASK-004: Database Schema (Prisma)

**PRD Reference**: Technical Specifications - Data Model
**Priority**: Critical | **Complexity**: L (4h) | **Type**: Feature | **Spec**: Backend

#### Description
Design and implement the Prisma schema for all entities: User, Case, CasePlan, Task, Document, AgentConversation.

#### Acceptance Criteria
- [ ] Prisma initialized in backend
- [ ] All entities from PRD defined
- [ ] Relations properly configured
- [ ] Enums for statuses and types
- [ ] Migration created and tested
- [ ] Seed script with sample data

#### Technical Approach
1. Install Prisma in server
2. Define schema based on PRD data model
3. Create initial migration
4. Write seed script

#### Files to Create
- `server/prisma/schema.prisma` - Database schema
- `server/prisma/seed.ts` - Seed data
- `server/prisma/migrations/` - Migration files

#### Dependencies
- **Blocked by**: TASK-001
- **Blocks**: TASK-005

---

### TASK-005: Backend API Setup (Express)

**PRD Reference**: Technical Specifications - Architecture
**Priority**: Critical | **Complexity**: M (4h) | **Type**: Feature | **Spec**: Backend

#### Description
Set up Express.js with middleware, error handling, route structure, and Prisma client integration.

#### Acceptance Criteria
- [ ] Express server with TypeScript
- [ ] CORS configured for frontend
- [ ] Error handling middleware
- [ ] Route structure (auth, cases, tasks, documents, agents)
- [ ] Prisma client integrated
- [ ] Health check endpoint

#### Technical Approach
1. Configure Express with middleware
2. Set up route modules
3. Integrate Prisma client
4. Add logging (pino)
5. Configure environment variables

#### Files to Create
- `server/src/app.ts` - Express app config
- `server/src/routes/index.ts` - Route aggregator
- `server/src/middleware/` - Error, auth middleware
- `server/src/lib/prisma.ts` - Prisma client

#### Dependencies
- **Blocked by**: TASK-004
- **Blocks**: TASK-013, TASK-014, TASK-015, TASK-016, TASK-017

---

### TASK-008: Dashboard Page

**PRD Reference**: FR-008, US-005
**Priority**: High | **Complexity**: L (6h) | **Type**: Feature | **Spec**: Frontend

#### Description
Build the main dashboard with case statistics cards, recent cases list, upcoming deadlines, and workload chart.

#### Acceptance Criteria
- [ ] Statistics cards (total cases, active, completed)
- [ ] Recent cases list with status badges
- [ ] Upcoming deadlines section
- [ ] Workload distribution chart (using recharts)
- [ ] Responsive layout
- [ ] Loading skeletons

#### Technical Approach
1. Create dashboard route/page
2. Build StatCard component
3. Build RecentCases component
4. Build DeadlinesList component
5. Add chart for workload
6. Connect to API (mock first)

#### Files to Create
- `src/pages/dashboard.tsx` - Dashboard page
- `src/components/dashboard/stat-card.tsx`
- `src/components/dashboard/recent-cases.tsx`
- `src/components/dashboard/deadlines-list.tsx`
- `src/components/dashboard/workload-chart.tsx`

#### Dependencies
- **Blocked by**: TASK-007
- **Blocks**: TASK-024

---

### TASK-012: Kanban Board Component

**PRD Reference**: FR-004, US-002
**Priority**: Critical | **Complexity**: XL (10h) | **Type**: Feature | **Spec**: Frontend

#### Description
Build a drag-and-drop Kanban board for task management with columns: Backlog, Em Andamento, Aguardando, Concluído.

#### Acceptance Criteria
- [ ] 4 default columns with Portuguese labels
- [ ] Drag-and-drop between columns (dnd-kit)
- [ ] Task cards with priority, due date, title
- [ ] Add task quick-form
- [ ] Edit task modal
- [ ] Delete task confirmation
- [ ] Persist order changes
- [ ] Optimistic updates

#### Technical Approach
1. Install @dnd-kit/core and @dnd-kit/sortable
2. Create KanbanColumn component
3. Create TaskCard component
4. Implement drag handlers
5. Connect to task API
6. Add animations

#### Files to Create
- `src/components/kanban/kanban-board.tsx`
- `src/components/kanban/kanban-column.tsx`
- `src/components/kanban/task-card.tsx`
- `src/components/kanban/add-task-form.tsx`
- `src/hooks/use-kanban.ts` - State logic

#### Dependencies
- **Blocked by**: TASK-011
- **Blocks**: TASK-024

---

### TASK-017: Agent Orchestrator (LangChain)

**PRD Reference**: Technical Specifications - AI Agent Implementation
**Priority**: Critical | **Complexity**: L (6h) | **Type**: Feature | **Spec**: Backend

#### Description
Create the LangChain.js orchestrator service that manages agent definitions, invocations, memory, and tool execution.

#### Acceptance Criteria
- [ ] LangChain.js installed and configured
- [ ] Agent base class defined
- [ ] OpenAI integration working
- [ ] Agent memory system (per case)
- [ ] Tool execution framework
- [ ] Streaming response handler
- [ ] Error handling with fallbacks

#### Technical Approach
1. Install langchain, @langchain/openai
2. Create BaseAgent class
3. Define agent schema in DB
4. Implement memory with ConversationBufferMemory
5. Create streaming handler
6. Add token usage tracking

#### Files to Create
- `server/src/agents/base-agent.ts` - Base class
- `server/src/agents/agent-registry.ts` - Agent definitions
- `server/src/agents/tools/` - Agent tools
- `server/src/services/agent-orchestrator.ts` - Main service
- `server/src/routes/agents.ts` - Agent API routes

#### Dependencies
- **Blocked by**: TASK-005
- **Blocks**: TASK-018, TASK-019, TASK-020, TASK-021, TASK-022

---

### TASK-018: ESTRATÉGIA Agent

**PRD Reference**: FR-002
**Priority**: Critical | **Complexity**: L (6h) | **Type**: Feature | **Spec**: Backend

#### Description
Implement the ESTRATÉGIA (Strategy) agent that creates comprehensive case plans from client intake.

#### Acceptance Criteria
- [ ] System prompt for Brazilian legal strategy
- [ ] Input: case details, case type
- [ ] Output: structured plan with legal basis, timeline
- [ ] Tools: lookup_law, search_jurisprudence (mocked)
- [ ] Save plan to database
- [ ] Streaming responses

#### Technical Approach
1. Define ESTRATÉGIA system prompt (Portuguese)
2. Create output schema (Zod)
3. Implement plan generation chain
4. Add specialized tools
5. Test with sample cases

#### Files to Create
- `server/src/agents/estrategia/index.ts`
- `server/src/agents/estrategia/prompt.ts`
- `server/src/agents/estrategia/tools.ts`
- `server/src/agents/estrategia/schema.ts`

#### Dependencies
- **Blocked by**: TASK-017
- **Blocks**: TASK-024

---

### TASK-023: Agent Chat UI Panel

**PRD Reference**: UI/UX - Agent Chat
**Priority**: High | **Complexity**: L (6h) | **Type**: Feature | **Spec**: Frontend

#### Description
Create the agent interaction panel with chat interface, agent selection, and streaming response display.

#### Acceptance Criteria
- [ ] Slide-out panel or modal
- [ ] Agent selection dropdown (5 agents)
- [ ] Chat message list
- [ ] User input with send button
- [ ] Streaming response display (typewriter effect)
- [ ] Save/export response option
- [ ] Loading states
- [ ] Error handling

#### Technical Approach
1. Create AgentPanel sheet component
2. Build ChatMessage component
3. Implement streaming handler
4. Connect to agent API
5. Add typewriter animation

#### Files to Create
- `src/components/agents/agent-panel.tsx`
- `src/components/agents/agent-selector.tsx`
- `src/components/agents/chat-message.tsx`
- `src/components/agents/chat-input.tsx`
- `src/hooks/use-agent-chat.ts`

#### Dependencies
- **Blocked by**: TASK-003, TASK-017
- **Blocks**: TASK-025

---

### TASK-027: LGPD Compliance Implementation

**PRD Reference**: NFR-002, Security Considerations
**Priority**: Critical | **Complexity**: M (4h) | **Type**: Feature | **Spec**: Full-stack

#### Description
Implement LGPD compliance features: consent capture, privacy policy display, data subject rights, audit logging.

#### Acceptance Criteria
- [ ] Consent checkbox on registration
- [ ] Privacy policy page
- [ ] Cookie consent banner
- [ ] Data export (portability)
- [ ] Account deletion option
- [ ] Audit log for data access
- [ ] DPO contact display

#### Technical Approach
1. Add consent fields to User model
2. Create privacy policy page
3. Add cookie consent component
4. Implement data export endpoint
5. Add audit logging middleware
6. Create data deletion flow

#### Files to Create
- `src/pages/privacy-policy.tsx`
- `src/components/cookie-consent.tsx`
- `server/src/middleware/audit-log.ts`
- `server/src/routes/data-rights.ts`

#### Dependencies
- **Blocked by**: TASK-024
- **Blocks**: TASK-028

---

## Task Prioritization Matrix

```
                    High Impact
                        │
    TASK-001,002,004   │   TASK-008,012,017,018
    TASK-003,005       │   TASK-023,024,027
         ┌─────────────┼─────────────┐
         │  FOUNDATION │   CRITICAL  │
         │             │             │
Low      │─────────────┼─────────────│ High
Urgency  │             │             │ Urgency
         │   DEFER     │   SCHEDULE  │
         │             │             │
         └─────────────┼─────────────┘
    TASK-028           │   TASK-019,020,021
                       │   TASK-022,025,026
                    Low Impact
```

---

## Notes for Agent DEV

1. **Start with Phase 1** - All other phases depend on foundation work
2. **Frontend and Backend can be parallel** after TASK-001
3. **Agent tasks (Phase 4) require OpenAI API key** - ensure .env is configured
4. **Kanban (TASK-012)** is the most complex frontend task - allocate extra time
5. **Test with mock data first** before full backend integration

---

## Change Log

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2025-12-10 | Agent TASKS | Initial decomposition |
