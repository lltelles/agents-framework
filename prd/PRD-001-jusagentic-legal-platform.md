# PRD: JusAgentic - AI-Powered Legal Workflow Platform

> **PRD ID**: PRD-001
> **Title**: JusAgentic Legal Platform
> **Status**: Draft
> **Created**: 2025-12-10
> **Author**: Agent PLAN
> **Story Reference**: User Story - AI-Assisted Legal Workflow Platform for Brazilian Law Firms

---

## Executive Summary

JusAgentic is a web-based AI-powered platform that transforms how Brazilian law firms and solo lawyers manage their cases and legal work. Inspired by AI-assisted development workflows, it enables lawyers to structure cases as plans, decompose them into actionable tasks, and leverage specialized "Legal AI Agents" to assist with research, document drafting, analysis, and review—all focused on Brazilian law. The platform features a dark-mode interface with a comprehensive dashboard and Kanban-style task management.

## Problem Statement

### Current State
- Lawyers manually manage complex cases with fragmented tools (spreadsheets, documents, generic project management)
- Legal research on Brazilian law is time-consuming and requires deep expertise
- Solo lawyers lack the support of a full legal team
- Case progress tracking is often disorganized
- Document drafting and review processes are repetitive and error-prone

### Desired State
- A unified platform where lawyers can structure cases from intake to resolution
- AI agents that assist with specific legal tasks (research, drafting, analysis, review)
- Clear visibility of case progress through dashboards and Kanban boards
- Automated assistance that understands Brazilian legal context (CLT, CPC, CDC, LGPD, etc.)
- A single lawyer can operate with the efficiency of a full legal team

### Business Value
- **Time Savings**: 40-60% reduction in routine legal research and drafting time
- **Case Capacity**: Solo lawyers can handle 2-3x more cases
- **Quality**: Consistent, reviewed outputs aligned with Brazilian legal standards
- **Visibility**: Real-time insight into case status and workload

## User Stories

### Primary Story
```
As a Brazilian lawyer
I want an AI-powered platform that helps me manage cases with specialized legal agents
So that I can work as efficiently as a full legal team while maintaining quality
```

### Supporting Stories

#### US-001: Case Planning
```
As a lawyer
I want to create a comprehensive case plan from an initial consultation
So that I have a structured approach to handling the case
```

**Acceptance Criteria**:
- [ ] Given a new client intake, when I provide case details, then the ESTRATÉGIA agent creates a structured case plan
- [ ] Given a case plan, when I review it, then I can approve, modify, or request regeneration
- [ ] Given an approved plan, when I save it, then it's stored with the case record

#### US-002: Task Decomposition
```
As a lawyer
I want my case plan to be broken down into actionable legal tasks
So that I can track progress and assign work appropriately
```

**Acceptance Criteria**:
- [ ] Given an approved case plan, when I request decomposition, then the TAREFAS agent creates prioritized tasks
- [ ] Given tasks, when I view them, then I see deadlines, dependencies, and priority levels
- [ ] Given tasks, when I organize them, then I can use a Kanban board interface

#### US-003: Legal Research
```
As a lawyer
I want AI assistance with Brazilian legal research
So that I can quickly find relevant laws, jurisprudence, and doctrine
```

**Acceptance Criteria**:
- [ ] Given a legal question, when I invoke the PESQUISA agent, then I receive researched findings with citations
- [ ] Given research results, when I review them, then I see references to specific articles, laws, and court decisions
- [ ] Given research, when I save it, then it's linked to the relevant task/case

#### US-004: Document Drafting
```
As a lawyer
I want AI assistance in drafting legal documents
So that I can produce quality documents faster
```

**Acceptance Criteria**:
- [ ] Given a document requirement, when I invoke the REDAÇÃO agent, then I receive a draft aligned with Brazilian legal standards
- [ ] Given a draft, when I review it, then I can request revisions with specific feedback
- [ ] Given approved documents, when I export them, then they're formatted professionally

#### US-005: Case Dashboard
```
As a lawyer
I want a dashboard showing all my cases and their status
So that I can prioritize my work and track deadlines
```

**Acceptance Criteria**:
- [ ] Given multiple cases, when I view the dashboard, then I see an overview of all cases with status indicators
- [ ] Given upcoming deadlines, when I view the dashboard, then I see alerts for urgent items
- [ ] Given case metrics, when I view the dashboard, then I see workload distribution and progress charts

## Functional Requirements

| ID | Requirement | Priority | Story Ref |
|----|-------------|----------|-----------|
| FR-001 | Case creation with structured input forms | Must Have | US-001 |
| FR-002 | AI-powered case plan generation (ESTRATÉGIA agent) | Must Have | US-001 |
| FR-003 | Task decomposition engine (TAREFAS agent) | Must Have | US-002 |
| FR-004 | Kanban board for task management | Must Have | US-002 |
| FR-005 | Legal research assistant (PESQUISA agent) | Must Have | US-003 |
| FR-006 | Document drafting assistant (REDAÇÃO agent) | Must Have | US-004 |
| FR-007 | Document review agent (REVISÃO agent) | Should Have | US-004 |
| FR-008 | Dashboard with case overview | Must Have | US-005 |
| FR-009 | Deadline tracking and alerts | Should Have | US-005 |
| FR-010 | User authentication and authorization | Must Have | - |
| FR-011 | Case document storage and management | Should Have | US-004 |
| FR-012 | Dark mode by default | Must Have | - |
| FR-013 | Export documents to PDF/DOCX | Should Have | US-004 |
| FR-014 | Agent conversation history | Should Have | - |

### FR-001: Case Creation
**Description**: Users can create new cases with structured forms capturing client info, case type, timeline, and initial details.
**Validation**: New cases appear in dashboard and can be accessed/edited.

### FR-002: ESTRATÉGIA Agent (Case Planning)
**Description**: AI agent that transforms initial case intake into a comprehensive legal strategy/plan, identifying key legal issues, applicable laws, and recommended approach.
**Validation**: Generated plans include legal basis, timeline, and actionable recommendations.

### FR-003: TAREFAS Agent (Task Decomposition)
**Description**: AI agent that breaks down case plans into prioritized, actionable tasks with deadlines and dependencies.
**Validation**: Generated tasks are logical, sequenced, and include all necessary legal activities.

### FR-004: Kanban Board
**Description**: Drag-and-drop Kanban interface for organizing tasks across customizable columns (e.g., Backlog, Em Andamento, Aguardando, Concluído).
**Validation**: Tasks can be moved between columns with visual feedback and state persistence.

### FR-005: PESQUISA Agent (Legal Research)
**Description**: AI agent specialized in Brazilian legal research, capable of finding relevant legislation, jurisprudence, and doctrine.
**Validation**: Research outputs include proper citations and references to Brazilian legal sources.

### FR-006: REDAÇÃO Agent (Document Drafting)
**Description**: AI agent that drafts legal documents (petitions, contracts, parecer) following Brazilian legal formats and standards.
**Validation**: Generated documents follow proper legal formatting and language.

### FR-007: REVISÃO Agent (Document Review)
**Description**: AI agent that reviews documents for legal accuracy, consistency, and compliance with Brazilian standards.
**Validation**: Review outputs include specific feedback and suggested corrections.

## Non-Functional Requirements

| ID | Requirement | Category | Target |
|----|-------------|----------|--------|
| NFR-001 | Page load time | Performance | < 2000ms |
| NFR-002 | AI agent response time | Performance | < 30s for simple queries |
| NFR-003 | LGPD compliance | Security/Privacy | Full compliance |
| NFR-004 | HTTPS/TLS encryption | Security | Required |
| NFR-005 | WCAG 2.1 AA compliance | Accessibility | Required |
| NFR-006 | Mobile responsive | Usability | Required |
| NFR-007 | Data backup | Reliability | Daily backups |
| NFR-008 | Uptime | Availability | 99.5% |

### NFR-001: Performance
- Initial page load: < 2000ms
- Dashboard render: < 1500ms
- Kanban interactions: < 100ms
- AI agent response: < 30s (simple), < 120s (complex research)

### NFR-002: Security & LGPD Compliance
- **Data Processing Basis**: Documented consent or legitimate interest
- **Data Subject Rights**: Access, correction, deletion, portability
- **Data Minimization**: Only collect necessary case data
- **Encryption**: AES-256 at rest, TLS 1.3 in transit
- **Audit Logging**: All data access and modifications logged
- **Data Retention**: Configurable retention policies
- **Consent Management**: Explicit consent capture and withdrawal

### NFR-003: Accessibility
- WCAG 2.1 AA compliance
- Screen reader support
- Keyboard navigation
- Color contrast ratios > 4.5:1

## Technical Specifications

### Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         JusAgentic Frontend                              │
│                    (React + TypeScript + Vite)                          │
├─────────────────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐    │
│  │  Dashboard  │  │   Kanban    │  │  Case View  │  │   Agents    │    │
│  │  Component  │  │   Board     │  │  Component  │  │   Panel     │    │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘    │
├─────────────────────────────────────────────────────────────────────────┤
│                         State Management (Zustand/Context)               │
├─────────────────────────────────────────────────────────────────────────┤
│                         API Layer (REST + WebSocket)                     │
└─────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                         Backend API (Node.js/Express)                    │
├─────────────────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐    │
│  │   Auth      │  │   Cases     │  │   Tasks     │  │   Agent     │    │
│  │   Service   │  │   Service   │  │   Service   │  │   Orchestr. │    │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘    │
├─────────────────────────────────────────────────────────────────────────┤
│                    AI Agent Layer (LangChain.js)                         │
│  ┌───────────┐ ┌───────────┐ ┌───────────┐ ┌───────────┐ ┌───────────┐ │
│  │ESTRATÉGIA │ │  TAREFAS  │ │ PESQUISA  │ │  REDAÇÃO  │ │  REVISÃO  │ │
│  └───────────┘ └───────────┘ └───────────┘ └───────────┘ └───────────┘ │
├─────────────────────────────────────────────────────────────────────────┤
│                         LLM Provider (OpenAI/Azure/Anthropic)            │
└─────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                         Database Layer (PostgreSQL)                      │
└─────────────────────────────────────────────────────────────────────────┘
```

### AI Agent Implementation Strategy

> **Key Design Decision**: Implementing agents in a web platform (outside IDE)

The legal AI agents will be implemented using **LangChain.js** on the backend, which provides:

1. **Model Agnostic**: Support for multiple LLM providers (OpenAI, Anthropic, Azure)
2. **Agent Framework**: Built-in agent abstractions with tools and memory
3. **RAG Support**: Integration with vector stores for legal knowledge bases
4. **Streaming**: Real-time response streaming to the frontend

#### Agent Architecture

Each agent is defined as a LangChain agent with:
- **System Prompt**: Role definition and behavioral constraints (stored in DB)
- **Tools**: Specific functions the agent can call (legal DB queries, document templates)
- **Memory**: Conversation history within a case context
- **Output Parser**: Structured output for integration with the platform

```typescript
// Example Agent Definition
interface LegalAgent {
  id: string;
  name: string;           // e.g., "ESTRATÉGIA"
  role: string;           // "Estrategista Jurídico"
  systemPrompt: string;   // Detailed instructions
  tools: AgentTool[];     // Available tools/functions
  outputSchema: ZodSchema; // Expected output structure
}
```

### Technology Stack

| Layer | Technology | Justification |
|-------|------------|---------------|
| Frontend | React 19 + TypeScript | Modern, type-safe UI development |
| Build Tool | Vite 7 | Fast development and builds |
| Styling | Tailwind CSS 4 | Utility-first, dark mode support |
| UI Components | shadcn/ui | High-quality, customizable components |
| State Management | Zustand or React Context | Lightweight, TypeScript-friendly |
| Backend | Node.js + Express/Fastify | JavaScript ecosystem, easy frontend integration |
| AI Orchestration | LangChain.js | Model-agnostic, comprehensive agent framework |
| LLM Provider | OpenAI GPT-4 / Azure OpenAI | Best performance for complex legal reasoning |
| Database | PostgreSQL | Robust, ACID compliant, JSON support |
| ORM | Prisma | Type-safe database access |
| Authentication | Supabase Auth / Auth.js | Modern auth with LGPD compliance |
| File Storage | S3-compatible (MinIO/AWS) | Document storage |
| Hosting | Vercel/Railway + Supabase | Easy deployment, scaling |

### Data Model

#### Core Entities

```typescript
interface User {
  id: string;
  email: string;
  name: string;
  oabNumber?: string;        // OAB registration
  role: 'LAWYER' | 'ADMIN';
  createdAt: Date;
  updatedAt: Date;
}

interface Case {
  id: string;
  userId: string;
  title: string;
  clientName: string;
  caseType: CaseType;        // CIVIL, TRABALHISTA, PENAL, etc.
  status: CaseStatus;
  description: string;
  plan?: CasePlan;
  createdAt: Date;
  updatedAt: Date;
}

interface CasePlan {
  id: string;
  caseId: string;
  content: string;           // Markdown content
  legalBasis: string[];      // Referenced laws
  strategy: string;
  timeline: PlanTimeline[];
  status: 'DRAFT' | 'APPROVED';
  createdAt: Date;
}

interface Task {
  id: string;
  caseId: string;
  title: string;
  description: string;
  status: TaskStatus;        // BACKLOG, IN_PROGRESS, WAITING, DONE
  priority: 'LOW' | 'MEDIUM' | 'HIGH' | 'URGENT';
  dueDate?: Date;
  order: number;             // Position in column
  dependencies: string[];    // Task IDs
  agentId?: string;          // If created by agent
  createdAt: Date;
  updatedAt: Date;
}

interface AgentConversation {
  id: string;
  caseId: string;
  taskId?: string;
  agentType: AgentType;      // ESTRATEGIA, TAREFAS, PESQUISA, REDACAO, REVISAO
  messages: ConversationMessage[];
  createdAt: Date;
}

interface Document {
  id: string;
  caseId: string;
  taskId?: string;
  title: string;
  type: DocumentType;        // PETICAO, CONTRATO, PARECER, etc.
  content: string;
  storageUrl: string;
  version: number;
  createdAt: Date;
}
```

#### Entity Relationships

```
[User] ──1:N──▶ [Case]
[Case] ──1:1──▶ [CasePlan]
[Case] ──1:N──▶ [Task]
[Case] ──1:N──▶ [Document]
[Case] ──1:N──▶ [AgentConversation]
[Task] ──N:1──▶ [Document]
```

## UI/UX Specifications

### Design System
- **Theme**: Dark mode by default (with light mode toggle)
- **Primary Color**: Deep blue/indigo (#3B82F6 range)
- **Accent Color**: Emerald green for success states
- **Typography**: Inter or similar professional sans-serif
- **Components**: shadcn/ui with custom legal-themed variants

### Key Screens

1. **Dashboard** (`/dashboard`)
   - Case statistics cards
   - Recent cases list
   - Upcoming deadlines calendar
   - Workload distribution chart

2. **Case List** (`/cases`)
   - Filterable, searchable case table
   - Quick status indicators
   - Bulk actions

3. **Case Detail** (`/cases/:id`)
   - Case information header
   - Tabbed sections: Plan, Tasks, Documents, Research
   - Agent interaction panel (slide-out)

4. **Kanban Board** (`/cases/:id/tasks`)
   - Drag-and-drop columns
   - Task cards with priority indicators
   - Quick-add task functionality

5. **Agent Chat** (Modal/Panel)
   - Conversation interface
   - Agent selection dropdown
   - Response streaming display
   - Save/export actions

### User Flow

```
[Login] → [Dashboard]
              │
              ├── [New Case] → [Case Form] → [Generate Plan] → [Approve Plan]
              │                                                      │
              │                                               [Generate Tasks]
              │                                                      │
              └── [Case List] → [Case Detail] ──────────────────────┘
                                     │
                                     ├── [Kanban Board] ← Task Management
                                     │
                                     ├── [Agent Panel] ← AI Interactions
                                     │
                                     └── [Documents] ← Draft/Review
```

## Security Considerations

### Threat Model

| Threat | Risk Level | Mitigation |
|--------|------------|------------|
| Unauthorized data access | High | Authentication, RBAC, row-level security |
| Data breach | High | Encryption, audit logs, minimal data retention |
| AI data leakage | Medium | No PII in prompts, data anonymization |
| Session hijacking | Medium | Secure cookies, short session expiry |
| XSS/CSRF attacks | Medium | CSP headers, CSRF tokens, input sanitization |

### LGPD Compliance Checklist

- [ ] Consent capture for data processing
- [ ] Privacy policy with clear data usage explanation
- [ ] Data subject rights portal (access, correction, deletion)
- [ ] Data processing records (ROPA)
- [ ] Encryption at rest and in transit
- [ ] Audit logging for all data access
- [ ] Data retention policy implementation
- [ ] DPO contact information display
- [ ] Cookie consent banner
- [ ] Cross-border transfer documentation (if using US LLM providers)

## Testing Strategy

### Unit Tests
- [ ] React component tests (Vitest + Testing Library)
- [ ] Agent prompt/response validation
- [ ] State management logic
- [ ] Utility functions

### Integration Tests
- [ ] API endpoint tests
- [ ] Database operations
- [ ] Agent orchestration flow
- [ ] Authentication flows

### End-to-End Tests (Playwright)
- [ ] Complete case creation flow 
- [ ] Task management (Kanban operations)
- [ ] Agent conversation flows
- [ ] Document generation and export

### Manual Testing
- [ ] Accessibility audit
- [ ] Mobile responsiveness
- [ ] Dark/light mode switching
- [ ] Edge cases in legal document generation

## Dependencies

### External Dependencies

| Dependency | Type | Fallback |
|------------|------|----------|
| OpenAI API / Azure OpenAI | Required | Anthropic Claude |
| PostgreSQL Database | Required | Supabase hosted |
| File Storage (S3) | Required | Local storage for dev |

### Internal Dependencies
- shadcn/ui component installation
- Prisma schema setup
- LangChain.js agent definitions

## Out of Scope

The following items are explicitly **NOT** part of this initial release:

1. **Multi-tenancy** - Single firm focus first
2. **Billing/Subscription** - Free during MVP phase
3. **Public legal database integration** - Initial focus on AI generation
4. **Mobile native app** - Responsive web only
5. **Real-time collaboration** - Single user per case
6. **Court system integrations (PJe, e-SAJ)** - Future enhancement
7. **Voice input/dictation** - Future enhancement
8. **Offline mode** - Online-only initially

## Risks and Mitigations

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| AI hallucinations in legal advice | High | High | Clear disclaimers, human review required, citation validation |
| LLM API costs | Medium | Medium | Token budgeting, caching, model selection |
| LGPD compliance gaps | Medium | High | Legal review, privacy-by-design, DPO consultation |
| Complex legal domain accuracy | High | Medium | Specialized prompts, Brazilian law training data |
| User adoption | Medium | Medium | Intuitive UX, onboarding flow, documentation |

## Success Metrics

### Launch Criteria
- [ ] All Must Have functional requirements implemented
- [ ] All tests passing
- [ ] LGPD compliance checklist complete
- [ ] Performance targets met
- [ ] Dark mode and responsive design verified
- [ ] Agent integration functional

### Success Metrics (Post-Launch)
| Metric | Target | Measurement |
|--------|--------|-------------|
| User activation | 70% create first case | Analytics |
| Case completion rate | 50% cases reach Concluído | Database query |
| Agent usage | 80% cases use at least 1 agent | Analytics |
| User satisfaction | NPS > 40 | In-app survey |
| Time to first document | < 30 minutes | Analytics |

## Timeline (Estimated)

| Milestone | Target | Dependencies |
|-----------|--------|--------------|
| PRD Approved | Week 1 | User review |
| Design System Setup | Week 2 | PRD Approved |
| Core UI Components | Week 3 | Design System |
| Backend API + Database | Week 4 | - |
| Agent Integration | Week 5-6 | Backend API |
| Dashboard + Kanban | Week 4-5 | Core UI |
| Testing + Polish | Week 7 | All features |
| MVP Launch | Week 8 | Testing complete |

---

## Appendix

### Glossary

| Term | Definition |
|------|------------|
| LGPD | Lei Geral de Proteção de Dados - Brazilian data protection law |
| OAB | Ordem dos Advogados do Brasil - Brazilian Bar Association |
| CLT | Consolidação das Leis do Trabalho - Labor law consolidation |
| CPC | Código de Processo Civil - Civil procedure code |
| CDC | Código de Defesa do Consumidor - Consumer protection code |
| Petição | Legal petition/motion document |
| Parecer | Legal opinion document |
| PJe | Processo Judicial Eletrônico - Electronic court system |

### Legal AI Agents Summary

| Agent | Portuguese Name | Role |
|-------|-----------------|------|
| ESTRATÉGIA | Estrategista | Creates case plans from intake |
| TAREFAS | Gestor de Tarefas | Decomposes plans into tasks |
| PESQUISA | Pesquisador | Conducts legal research |
| REDAÇÃO | Redator | Drafts legal documents |
| REVISÃO | Revisor | Reviews documents for quality |

### Open Questions

- [ ] Which LLM provider (OpenAI vs Azure OpenAI vs Anthropic) for production?
- [ ] Self-hosted backend or serverless (Supabase Edge Functions)?
- [ ] Brazilian legal knowledge base source for RAG enhancement?

---

## Change Log

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2025-12-10 | Agent PLAN | Initial draft |
