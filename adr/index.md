# Architecture Decision Records (ADR) Index

> This document serves as the central registry for all Architecture Decision Records in this project.

## 📋 What are ADRs?

Architecture Decision Records (ADRs) capture important architectural decisions made during the project lifecycle. They provide context, rationale, and consequences for decisions that affect the system's architecture, security, and coding standards.

## 🎯 Purpose in the AI-Assisted Framework

ADRs are the foundation of consistency in our AI-assisted development workflow:

- **Agent PLAN** references ADRs when creating PRDs
- **Agent TASKS** ensures tasks align with ADRs
- **Agent DEV** implements following ADR specifications
- **Agent REV** validates compliance with ADRs

## 📊 ADR Registry

| ID | Title | Status | Category | Date |
|----|-------|--------|----------|------|
| ADR-001 | [Template] | Template | - | - |
| | | | | |

### Status Legend
- **Proposed**: Under discussion
- **Accepted**: Approved and active
- **Deprecated**: No longer applies to new work
- **Superseded**: Replaced by another ADR

### Categories
- **Architecture**: System structure and design
- **Security**: Security policies and practices
- **Patterns**: Code patterns and conventions
- **Technology**: Technology choices
- **Process**: Development process decisions

## 🗂️ ADRs by Category

### Architecture
- [List architecture ADRs here]

### Security
- [List security ADRs here]

### Patterns
- [List pattern ADRs here]

### Technology
- [List technology ADRs here]

### Process
- [List process ADRs here]

## ✨ Creating New ADRs

Use the template at `/.ai/adr/template.md` or run:

```
/adr create "[Title]" --category=[category]
```

## 📐 ADR Naming Convention

```
ADR-[NNN]-[short-title].md

Examples:
- ADR-001-use-typescript-strict-mode.md
- ADR-002-react-query-for-data-fetching.md
- ADR-015-authentication-with-oauth2.md
```

## 🔗 Quick Links

- [ADR Template](./template.md)
- [How to Write Good ADRs](https://adr.github.io/)

---

**Last Updated**: [Update when ADRs change]
