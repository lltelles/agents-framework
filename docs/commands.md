# Commands Reference

> Essential commands for controlling the AI-Assisted Development Framework

---

## 🎮 Core Commands

### `/init` - Initialize Context

Updates the application context to prevent AI hallucinations by providing current project state.

```
/init
```

**What it does**:
1. Scans the project structure
2. Identifies key configuration files
3. Catalogs existing ADRs
4. Maps the tech stack
5. Updates `/.ai/context.md`

**When to use**:
- At the start of a new session
- After major changes to the codebase
- When the AI seems to be making incorrect assumptions
- Before starting a new feature

**Output**:
```markdown
# Project Context

## Project Overview
- Name: [project-name]
- Type: React + TypeScript
- Updated: [timestamp]

## Tech Stack
- Framework: React 18.x
- Language: TypeScript 5.x
- State Management: [library]
- ...

## Structure
[Key directories and their purposes]

## Active ADRs
[List of current ADRs]
```

---

### `/clear` - Clear Context

Clears the current context between tasks to maintain predictability.

```
/clear
```

**What it does**:
1. Resets agent memory
2. Clears task-specific context
3. Maintains project-level context from `/init`

**When to use**:
- Between different tasks
- When switching features
- After completing a review cycle
- When the AI context seems polluted

**Options**:
```
/clear              # Clear task context only
/clear --all        # Clear everything including project context
/clear --agents     # Reset agent states only
```

---

### `/agents` - Manage Agents

Lists, creates, or updates AI agents.

```
/agents [action] [options]
```

**Actions**:

#### List all agents
```
/agents list
```

Output:
```
Available Agents:
┌──────────┬─────────────────────────┬──────────┐
│ Agent    │ Role                    │ Status   │
├──────────┼─────────────────────────┼──────────┤
│ PLAN     │ Business Analyst        │ Active   │
│ TASKS    │ Tech Lead               │ Active   │
│ DEV      │ Developer               │ Active   │
│ REV      │ Code Reviewer           │ Active   │
└──────────┴─────────────────────────┴──────────┘
```

#### Create a Specialist Agent
```
/agents create specialist "[Name]" --focus="[expertise areas]"
```

Example:
```
/agents create specialist "Tech Lead" --focus="system architecture, technical decisions, code standards"
```

#### Create a Specific Agent
```
/agents create specific "[Name]" --artifact="[artifact type]"
```

Example:
```
/agents create specific "BigQuery Modeler" --artifact="BigQuery data models and schemas"
```

#### Update an Agent
```
/agents update [AGENT_NAME] --add="[new capability]"
/agents update [AGENT_NAME] --remove="[capability]"
```

#### Delete a Custom Agent
```
/agents delete [AGENT_NAME]
```

---

### `/status` - Show Workflow Status

Displays the current state of the development workflow.

```
/status
```

**Output**:
```
┌─────────────────────────────────────────────────────────────┐
│                    Workflow Status                          │
├─────────────────────────────────────────────────────────────┤
│ Current PRD: user-authentication.md                         │
│ Status: In Development                                      │
│                                                             │
│ Tasks Progress:                                             │
│ ████████████░░░░░░░░ 60% (6/10)                            │
│                                                             │
│ ✅ Completed: TASK-001, TASK-002, TASK-003, TASK-004       │
│ 🔄 In Progress: TASK-005, TASK-006                         │
│ ⏳ Pending: TASK-007, TASK-008, TASK-009, TASK-010         │
│                                                             │
│ Last Action: DEV completed TASK-004                         │
│ Next Suggested: @DEV frontend Implement TASK-007            │
└─────────────────────────────────────────────────────────────┘
```

---

### `/adr` - Manage ADRs

Lists or creates Architecture Decision Records.

```
/adr [action] [options]
```

**Actions**:

#### List all ADRs
```
/adr list
```

#### List by category
```
/adr list --category=security
```

#### Create a new ADR
```
/adr create "[Title]" --category=[category]
```

Example:
```
/adr create "Use React Query for Data Fetching" --category=patterns
```

#### Show specific ADR
```
/adr show ADR-001
```

---

## 🤖 Agent Invocation Commands

### Invoke PLAN Agent
```
@PLAN Create a PRD for: [user story or feature description]
```

Options:
```
@PLAN Create a PRD for: [story] --focus=security
@PLAN Create a PRD for: [story] --template=minimal
@PLAN Review existing PRD at: [path]
```

### Invoke TASKS Agent
```
@TASKS Decompose the PRD at: [path]
```

Options:
```
@TASKS Decompose with backend-first approach
@TASKS Decompose only the API section
@TASKS Re-prioritize tasks based on: [criteria]
```

### Invoke DEV Agent
```
@DEV [specialization] Implement task: [TASK-XXX]
```

Specializations:
- `backend` - Server-side implementation
- `frontend` - UI implementation
- `fullstack` - End-to-end implementation

Examples:
```
@DEV backend Implement TASK-003
@DEV frontend Implement TASK-007 with focus on accessibility
@DEV fullstack Implement TASK-012
```

### Invoke REV Agent
```
@REV Review the implementation for task: [TASK-XXX]
```

Options:
```
@REV Review with security focus: TASK-005
@REV Review only the tests for: TASK-003
@REV Re-review after changes: TASK-005
```

---

## 📋 Workflow Commands

### `/start` - Start New Feature

Initiates a new feature workflow from scratch.

```
/start "[Feature Name]"
```

This command:
1. Creates a new PRD shell
2. Invokes Agent PLAN
3. Sets up tracking

### `/complete` - Complete Current Task

Marks the current task as complete and suggests next steps.

```
/complete [TASK-XXX]
```

### `/review` - Request Review

Triggers a review cycle for completed work.

```
/review [TASK-XXX]
```

### `/ship` - Prepare for Deployment

Runs final checks before merging.

```
/ship
```

This command:
1. Verifies all tasks complete
2. Runs full test suite
3. Validates ADR compliance
4. Generates summary report

---

## 🔧 Utility Commands

### `/help` - Show Help

```
/help              # General help
/help [command]    # Specific command help
/help agents       # Help with agents
```

### `/config` - Configure Framework

```
/config show                  # Show current config
/config set [key] [value]     # Set config value
```

Configuration options:
```
/config set default-dev-mode fullstack
/config set auto-review true
/config set task-complexity-threshold L
```

### `/export` - Export Artifacts

```
/export prd [name] --format=pdf
/export tasks [prd-name] --format=csv
/export timeline [prd-name] --format=gantt
```

---

## 📌 Quick Reference

| Command | Purpose |
|---------|---------|
| `/init` | Update project context |
| `/clear` | Clear task context |
| `/agents` | Manage agents |
| `/status` | Show workflow status |
| `/adr` | Manage ADRs |
| `@PLAN` | Invoke Planning Agent |
| `@TASKS` | Invoke Tasks Agent |
| `@DEV` | Invoke Development Agent |
| `@REV` | Invoke Review Agent |
| `/start` | Start new feature |
| `/complete` | Complete task |
| `/review` | Request review |
| `/ship` | Prepare for deployment |
| `/help` | Show help |
| `/config` | Configure framework |
| `/export` | Export artifacts |

---

## 💡 Tips

1. **Always `/init` at session start** - This prevents hallucinations
2. **Use `/clear` between tasks** - Keeps context focused
3. **Check `/status` regularly** - Stay oriented in the workflow
4. **Create ADRs for new patterns** - Future you will thank you
5. **Use specific agent modes** - `@DEV backend` is more focused than `@DEV fullstack`
