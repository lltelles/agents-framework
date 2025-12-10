# Complete Workflow Guide

> Step-by-step guide for using the AI-Assisted Development Framework

---

## 🎯 Overview

The AI-Assisted Development Framework transforms a single developer into a complete team by using specialized AI agents that automate the entire development cycle. This guide walks you through the complete workflow from story to shipped code.

## 📋 Prerequisites

Before starting, ensure you have:

1. ✅ The `.ai` folder copied to your project root
2. ✅ Your AI assistant configured (GitHub Copilot, Cursor, etc.)
3. ✅ At least one ADR defined for your project
4. ✅ Understanding of the core commands

---

## 🚀 Phase 1: Initialization

### Step 1.1: Initialize Project Context

At the start of every session:

```
/init
```

This scans your project and creates/updates `/.ai/context.md` with:
- Project structure
- Tech stack details
- Available ADRs
- Existing patterns

**Why it matters**: This prevents AI hallucinations by grounding the agents in your actual project reality.

### Step 1.2: Create Initial ADRs (First Time Only)

If this is a new project, create foundational ADRs:

```
/adr create "Use TypeScript Strict Mode" --category=patterns
/adr create "React Component Structure" --category=patterns
/adr create "API Error Handling" --category=patterns
/adr create "Authentication with JWT" --category=security
```

**Tip**: Start with 3-5 ADRs covering your most important patterns. Add more as you make decisions.

---

## 📝 Phase 2: Planning

### Step 2.1: Capture the User Story

Have your user story or feature request ready:

```
As a user, I want to reset my password via email
so that I can regain access to my account if I forget my password.

Acceptance Criteria:
- User can request password reset from login page
- Email with reset link is sent within 1 minute
- Link expires after 24 hours
- User must set a new password meeting security requirements
- User receives confirmation after successful reset
```

### Step 2.2: Invoke the PLAN Agent

```
@PLAN Create a PRD for: 

As a user, I want to reset my password via email so that I can regain access 
to my account if I forget my password.

[Paste full story with acceptance criteria]
```

### Step 2.3: Review the PRD

Agent PLAN will generate a comprehensive PRD. Review it for:

- [ ] All acceptance criteria are captured
- [ ] Correct ADRs are referenced
- [ ] Technical specifications are accurate
- [ ] Security considerations are adequate
- [ ] Out of scope is clearly defined

**Make corrections**: Ask PLAN to revise specific sections if needed.

### Step 2.4: Approve the PRD

Once satisfied:

```
@PLAN Approve the PRD and save to /.ai/prd/password-reset.md
```

---

## 📊 Phase 3: Task Decomposition

### Step 3.1: Invoke the TASKS Agent

```
@TASKS Decompose the PRD at /.ai/prd/password-reset.md
```

### Step 3.2: Review the Task Board

Agent TASKS will create:
- A task board with all tasks
- Individual task files
- Dependency graph
- Execution phases

Review for:
- [ ] All PRD requirements have tasks
- [ ] Dependencies are logical
- [ ] Complexity estimates are realistic
- [ ] Critical path is identified

### Step 3.3: Adjust if Needed

```
@TASKS Split TASK-003 into smaller tasks
@TASKS Add a task for error handling in the email service
@TASKS Re-prioritize TASK-005 as critical
```

### Step 3.4: Finalize Task Board

```
@TASKS Finalize and save to /.ai/tasks/password-reset/
```

---

## 💻 Phase 4: Development

### Step 4.1: Check Workflow Status

```
/status
```

This shows you which task to work on next.

### Step 4.2: Start with First Task

Follow the execution order from the task board. For example:

```
@DEV backend Implement task: TASK-001 - Create password reset request endpoint
```

### Step 4.3: Development Process

For each task, Agent DEV will:

1. Read the task specification
2. Check applicable ADRs
3. Examine existing code patterns
4. Implement the solution
5. Write tests
6. Add documentation

### Step 4.4: Clear Context Between Tasks

After completing each task:

```
/clear
```

This ensures the next task starts with a clean context.

### Step 4.5: Continue Through Tasks

Repeat for each task:

```
@DEV backend Implement task: TASK-002 - Generate secure reset token
/clear
@DEV backend Implement task: TASK-003 - Send reset email
/clear
@DEV frontend Implement task: TASK-004 - Password reset request form
```

**Tip**: Use the appropriate specialization:
- `backend` for server-side tasks
- `frontend` for UI tasks
- `fullstack` for end-to-end tasks

---

## 🔍 Phase 5: Review

### Step 5.1: Request Review for Each Task

After implementing a task:

```
@REV Review the implementation for task: TASK-001
```

### Step 5.2: Address Review Findings

Agent REV will provide:
- Blocking issues (must fix)
- Suggestions (should consider)
- Positive feedback (what's good)

Address blocking issues:

```
@DEV backend Fix the validation issue in TASK-001 as per review feedback
```

### Step 5.3: Re-review if Needed

```
@REV Re-review TASK-001 after addressing feedback
```

### Step 5.4: Complete Task

Once review passes:

```
/complete TASK-001
```

---

## 🔄 Complete Workflow Example

Here's a complete session example:

```
# Session Start
/init

# Planning
@PLAN Create a PRD for: [User story]
# Review and approve PRD

# Task Decomposition
@TASKS Decompose the PRD at /.ai/prd/feature-name.md
# Review task board

# Development Cycle (repeat for each task)
/status
@DEV backend Implement task: TASK-001
@REV Review the implementation for task: TASK-001
# Fix any issues
/complete TASK-001
/clear

# Continue with next task
@DEV frontend Implement task: TASK-002
@REV Review the implementation for task: TASK-002
/complete TASK-002
/clear

# ... continue until all tasks complete ...

# Final Check
/status
/ship
```

---

## 📊 Workflow Diagram

```
┌──────────────────────────────────────────────────────────────────────────┐
│                         Complete Workflow                                 │
├──────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  ┌─────────┐                                                             │
│  │  /init  │ ─────────────────────────────────────────────────────────┐ │
│  └────┬────┘                                                           │ │
│       │                                                                │ │
│       ▼                                                                │ │
│  ┌─────────┐     ┌─────────┐                                          │ │
│  │▶  @PLAN  │────│   PRD   │                                          │ │
│  └─────────┘     └────┬────┘                                          │ │
│                       │                                                │ │
│                       ▼                                                │ │
│  ┌─────────┐     ┌─────────┐                                          │ │
│  │ @TASKS  │────▶│  Tasks  │                                          │ │
│  └─────────┘     └────┬────┘                                          │ │
│                       │                                                │ │
│       ┌───────────────┼───────────────┐                               │ │
│       │               │               │                               │ │
│       ▼               ▼               ▼                               │ │
│  ┌─────────┐     ┌─────────┐     ┌─────────┐                         │ │
│  │  Task 1 │     │  Task 2 │     │  Task N │                         │ │
│  └────┬────┘     └────┬────┘     └────┬────┘                         │ │
│       │               │               │                               │ │
│       ▼               ▼               ▼                               │ │
│  ┌─────────┐     ┌─────────┐     ┌─────────┐                         │ │
│  │  @DEV   │     │  @DEV   │     │  @DEV   │                         │ │
│  └────┬────┘     └────┬────┘     └────┬────┘                         │ │
│       │               │               │                               │ │
│       ▼               ▼               ▼                               │ │
│  ┌─────────┐     ┌─────────┐     ┌─────────┐                         │ │
│  │  @REV   │     │  @REV   │     │  @REV   │                         │ │
│  └────┬────┘     └────┬────┘     └────┬────┘                         │ │
│       │               │               │                               │ │
│       ▼               ▼               ▼                               │ │
│  ┌─────────┐     ┌─────────┐     ┌─────────┐                         │ │
│  │/complete│     │/complete│     │/complete│                         │ │
│  └────┬────┘     └────┬────┘     └────┬────┘                         │ │
│       │               │               │                               │ │
│       └───────────────┴───────────────┘                               │ │
│                       │                                                │ │
│                       ▼                                                │ │
│                  ┌─────────┐                                          │ │
│                  │  /ship  │                                          │ │
│                  └────┬────┘                                          │ │
│                       │                                                │ │
│                       ▼                                                │ │
│                  ┌─────────┐                                          │ │
│                  │  Done!  │◀─────────────────────────────────────────┘ │
│                  └─────────┘                                            │
│                                                                          │
│  Legend: ─▶ Flow   ◀─ ADR Reference (continuous)                        │
└──────────────────────────────────────────────────────────────────────────┘
```

---

## 🎯 Best Practices

### Do's ✅

1. **Always `/init` at session start** - Grounds the AI in reality
2. **Use `/clear` between tasks** - Prevents context pollution
3. **Follow the workflow order** - PLAN → TASKS → DEV → REV
4. **Create ADRs for new patterns** - Future consistency
5. **Review AI output carefully** - You're still responsible
6. **Iterate on PRDs** - Get them right before coding
7. **Use specific agent modes** - More focused results

### Don'ts ❌

1. **Don't skip the review phase** - Quality matters
2. **Don't ignore ADR violations** - They exist for a reason
3. **Don't batch too many tasks** - One at a time is clearer
4. **Don't forget to `/clear`** - Polluted context causes issues
5. **Don't blindly accept output** - Verify everything
6. **Don't skip tests** - Even if "it's simple"

---

## 🛠️ Troubleshooting

### AI seems confused about the project

```
/init           # Refresh context
/clear --all    # Clear everything
/init           # Re-initialize
```

### Tasks seem too big

```
@TASKS Split TASK-XXX into smaller tasks with 2-4 hour estimates
```

### Review is too strict/lenient

```
@REV Review with [strict|balanced|lenient] mode for: TASK-XXX
```

### Lost track of progress

```
/status
```

### Need a specialist not covered by core agents

```
/agents create specialist "Security Architect" --focus="security architecture, threat modeling, compliance"
```

---

## 📚 Next Steps

1. **Read the [Commands Reference](./commands.md)** - Full command documentation
2. **Review [Best Practices](./best-practices.md)** - Tips for success
3. **Create project ADRs** - Document your decisions
4. **Start your first feature** - Learn by doing!

---

**Remember**: The framework is a tool to augment your capabilities, not replace your judgment. Stay engaged, review carefully, and maintain ownership of the final product.
