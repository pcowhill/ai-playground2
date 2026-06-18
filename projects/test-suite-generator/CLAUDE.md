# CLAUDE.md — Test Suite Generator Project

This file orients any Claude session working on this project. Read it first.

## What this project is

A learning project that follows an **8-stage AI-assisted development workflow** as a deliberate
rehearsal of the process. The product being built is a **Python CLI tool that generates pytest
suites from Python source files using the Claude API**. See `brainstorm.md` for full project goals,
constraints, and definition of done.

The *process* matters as much as the *product*. The author is building intuition for AI-assisted
development to eventually advise their company (Roster-5 Software) on AI adoption.

## The 8-Stage Workflow

Each stage reads the prior stage's artifact, converses with the author, and produces its own
artifact. Stages are typically run in **separate Claude sessions** to rehearse clean handoffs and
keep context windows small (simulating a future multi-agent setup).

| # | Stage          | Reads             | Produces                  | Purpose |
|---|----------------|-------------------|---------------------------|---------|
| 1 | Brainstorm     | —                 | `brainstorm.md`           | Decide what's worth pursuing and why |
| 2 | Idea           | `brainstorm.md`   | `idea.md`                 | High-level summary of what the project accomplishes |
| 3 | Research       | `idea.md`         | `research.md`             | Learn what's needed via web search + planning |
| 4 | Prototype      | `research.md`     | `prototype/` + notes      | Validate feasibility; answer open technical questions |
| 5 | PRD            | `prototype/`      | `prd.md`                  | Product requirements + design of the implementation |
| 6 | Kanban         | `prd.md`          | `kanban/task-NNN.md` files | Dependency-aware tasks that can be parallelized across agents |
| 7 | Implementation | `kanban/`         | `implementation/` + PRs   | Write code, make/merge PRs, populate the codebase |
| 8 | QA / Testing   | everything        | updates to all artifacts  | Test (automated + human), iterate. Often the longest stage. |

## Conventions

- **Artifacts are the memory.** Each session starts cold; everything that must survive to the next
  stage goes into a markdown artifact. Each artifact starts with a "How to use this file" note for
  the next session.
- **Kanban tasks are individual files** (`kanban/task-001.md`, etc.) so an orchestrator agent can
  hand a single task to a worker agent without parsing the whole board.
- **Record decisions and resolved questions** in each artifact, plus explicit "input to the next
  stage" guidance.
- **Branch**: develop on `claude/sharp-goldberg-o6odwm`. Commit and push artifacts as stages complete.
- **Ask the author questions.** This is a collaborative, alignment-heavy process — don't run ahead
  silently.

## Directory layout

```
projects/test-suite-generator/
├── CLAUDE.md          ← this file
├── brainstorm.md      ← stage 1 (done)
├── idea.md            ← stage 2
├── research.md        ← stage 3
├── prototype/         ← stage 4 (throwaway validation code)
├── prd.md             ← stage 5
├── kanban/            ← stage 6 (task-NNN.md files)
└── implementation/    ← stage 7 (the real project code)
```

## Current status

- [x] Stage 1 — Brainstorm (`brainstorm.md`)
- [ ] Stage 2 — Idea
- [ ] Stage 3 — Research
- [ ] Stage 4 — Prototype
- [ ] Stage 5 — PRD
- [ ] Stage 6 — Kanban
- [ ] Stage 7 — Implementation
- [ ] Stage 8 — QA / Testing
