# SADS (Solo AI Dev System)

## Overview
This repository is the execution workspace for a Solo AI Development workflow.

Roles:
- ChatGPT: Product Architect (requirements, design, task planning)
- Codex App: Engineering Agent (implementation, testing, commits)
- GitHub: Single Source of Truth (state + artifacts)

---

## Core Principle
All development is driven by three synchronized artifacts:

- state/PROJECT_STATE.md → current stage & control state
- tasks/TASK_QUEUE.md → executable work items for Codex
- docs/ → product + architecture + specifications

---

## Initial Structure (to be created)

```
docs/
  PRD.md
  ARCHITECTURE.md

state/
  PROJECT_STATE.md
  ARTIFACT_INDEX.md

tasks/
  TASK_QUEUE.md

src/
tests/
```

---

## Workflow

1. ChatGPT generates PRD / Architecture / Tasks
2. Files are stored in GitHub repo
3. Codex App reads TASK_QUEUE.md
4. Codex implements tasks and pushes commits
5. ChatGPT reviews state and advances stage

---

## Minimal Protocol

PROJECT_STATE.md controls progression:

- stage: Problem → Solution → MVP → Build → QA → Release
- status: READY / BLOCKED / DONE
- next_task: pointer to TASK_QUEUE.md

---

## Rule Set

- No direct chat-based code execution
- No task ambiguity allowed
- Every task must be executable by Codex without clarification
- GitHub is the only memory layer
