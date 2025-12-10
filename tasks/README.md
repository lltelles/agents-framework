# Tasks Directory

This directory contains generated task files from Agent TASKS.

## Structure

After running `@TASKS` to decompose a PRD, you'll find:

```
tasks/
├── [prd-name]-board.md          # Task board overview
└── [prd-name]/                  # Individual task files
    ├── TASK-001.md
    ├── TASK-002.md
    └── ...
```

## Usage

1. Generate tasks: `@TASKS Decompose the PRD at /.ai/prd/[name].md`
2. Check status: `/status`
3. Implement: `@DEV [mode] Implement task: TASK-XXX`
4. Review: `@REV Review the implementation for task: TASK-XXX`
5. Complete: `/complete TASK-XXX`
