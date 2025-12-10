# AI-Assisted Development Framework

> A framework that transforms a single developer into a complete team through specialized AI agents that automate the entire development cycle while following project ADRs (Architecture Decision Records).

## 🎯 Overview

This framework provides a structured approach to AI-assisted development where specialized agents act as "virtual coworkers" that automate all stages of the development cycle. Each agent has a specific role, ensuring complete and validated delivery before code reaches the repository.

## 🤖 Core Agents

| Agent | Role Equivalent | Purpose |
|-------|-----------------|---------|
| **PLAN** | Business Analyst / Solution Architect | Creates comprehensive PRDs from user stories |
| **TASKS** | Tech Lead | Decomposes PRDs into prioritized technical tasks |
| **DEV** | Specialized Developer | Implements code, tests, and documentation |
| **REV** | Code Reviewer / Security Analyst | Reviews implementation for quality and compliance |

## 📁 Framework Structure

```
.ai/
├── agents/                    # Agent prompt templates
│   ├── PLAN.md               # Planning Agent
│   ├── TASKS.md              # Task Decomposition Agent
│   ├── DEV.md                # Development Agent
│   ├── REV.md                # Review Agent
│   └── templates/            # Templates for custom agents
│       ├── SPECIALIST.md     # For technical expertise (e.g., Tech Lead)
│       └── SPECIFIC.md       # For single artifacts (e.g., Data Modeling)
├── adr/                       # Architecture Decision Records
│   ├── template.md           # ADR template
│   └── index.md              # ADR index/registry
├── docs/                      # Framework documentation
│   ├── workflow.md           # Complete workflow guide
│   ├── commands.md           # Essential commands reference
│   └── best-practices.md     # Best practices and tips
├── prd/                       # Product Requirements Documents
│   └── template.md           # PRD template
├── tasks/                     # Generated task files
│   └── .gitkeep
└── context.md                 # Current project context (updated with /init)
```

## 🚀 Quick Start

### 1. Initialize the Framework

Copy the `.ai` folder to your project root and run:

```
/init
```

This updates the project context to prevent AI hallucinations.

### 2. Start with Planning

Export your user story and invoke the PLAN agent:

```
@PLAN Create a PRD for: [Your User Story]
```

### 3. Decompose into Tasks

Once the PRD is approved:

```
@TASKS Decompose the PRD into technical tasks
```

### 4. Implement

For each task:

```
@DEV [backend|frontend|fullstack] Implement task: [Task Reference]
```

### 5. Review

After implementation:

```
@REV Review the implementation for task: [Task Reference]
```

## 🎮 Essential Commands

| Command | Description |
|---------|-------------|
| `/init` | Updates application context to prevent hallucinations |
| `/clear` | Clears context between tasks for predictability |
| `/agents` | Lists, creates, or updates agents |
| `/status` | Shows current workflow status |
| `/adr` | Lists or creates Architecture Decision Records |

## 🔧 Creating Custom Agents

### Specialist Agents
For technical expertise spanning multiple artifacts:

```
/agents create specialist "Tech Lead" --focus="system architecture, technical decisions"
```

### Specific Agents
For single artifact focus:

```
/agents create specific "BigQuery Modeler" --artifact="data models"
```

## 📋 Workflow Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                    AI-Assisted Development Flow                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐  │
│  │   PLAN   │───▶│  TASKS   │───▶│   DEV    │───▶│   REV    │  │
│  │          │    │          │    │          │    │          │  │
│  │ PRD +    │    │ Task     │    │ Code +   │    │ Quality  │  │
│  │ ADR Refs │    │ Breakdown│    │ Tests    │    │ Check    │  │
│  └──────────┘    └──────────┘    └──────────┘    └──────────┘  │
│       │                              │               │          │
│       ▼                              ▼               ▼          │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                   ADR Repository                         │   │
│  │  (Architecture, Security, Patterns, Standards)          │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## 🎯 Benefits

- **Complete Team in One**: A single developer becomes a full team
- **Consistent Quality**: All code follows ADRs and project standards
- **Full Control**: Developer maintains control with essential commands
- **Predictable Delivery**: Validated before becoming repository code
- **Exponential Acceleration**: Dramatically speeds up planning and delivery

## 📚 Documentation

- [Complete Workflow Guide](./docs/workflow.md)
- [Commands Reference](./docs/commands.md)
- [Best Practices](./docs/best-practices.md)
- [ADR Guide](./adr/index.md)

## 🔗 Integration

This framework is designed to work with any AI coding assistant that supports:
- Custom prompts/instructions
- Context awareness
- Multi-turn conversations

Compatible with: GitHub Copilot, Cursor, Cody, Continue, and similar tools.

---

**License**: MIT
