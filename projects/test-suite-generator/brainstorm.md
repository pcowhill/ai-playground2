# Brainstorm — Automated Test Suite Generator

## How to use this file
This is the output of the Brainstorm stage. The **Idea stage** should read this file in full
before beginning. Its job is to take these inputs and — through conversation with the author —
produce a concrete, scoped `idea.md` that defines what the product is and what it should do.

---

## Stage: Brainstorm
## Date: 2026-06-18
## Author: Pat Wilcox

---

## What are we building (and why)?

A **CLI tool** (with potential for a simple web UI later) that accepts a Python source file as
input, sends it to the Claude API, and receives back a ready-to-run pytest test suite. The AI
generates the code; after that, the AI is not involved — only the generated tests run.

This is the author's **first project** using the 8-stage AI-assisted development workflow. The
code artifact is secondary to the learning goals below.

---

## Primary Learning Goals

1. **Evaluate AI-generated code**: Develop the skill and intuition to assess whether AI output is
   correct, trustworthy, and production-quality — not just syntactically valid.
2. **Experience the full 8-stage workflow**: Brainstorm → Idea → Research → Prototype → PRD →
   Kanban → Implementation → QA. Treat this project as a rehearsal of the process itself.
3. **Understand the AI-as-generator paradigm**: Gain hands-on experience with the class of
   problems where AI generates a static artifact (code) and then steps away, as distinct from
   problems where AI runs operationally at runtime.

---

## The Demo Moment

When showing this to a skeptical colleague:
> "Watch — I give it this Python file, and it reliably and intelligently produces tests that
> follow best software practices and faithfully validate the way an outsider would expect the
> classes and functions to operate."

The emphasis is on **reliability** and **faithfulness to expected behavior** — not just coverage
for coverage's sake.

---

## Constraints

- Must run **locally** — no cloud deployment required
- **No additional API costs** beyond the author's existing Claude Max plan
- Completable in a **few hours to a few days** of AI-assisted sessions

---

## Definition of Done

The project is complete when, given any reasonably well-structured Python file as input, the tool
produces a pytest suite that satisfies all four criteria:

1. Covers all **public functions and methods** in the source file
2. Follows **pytest conventions and best practices** (fixtures, clear naming, no redundant
   assertions)
3. **Runs without modification** — `pytest` passes on the generated file out of the box
4. **Catches real bugs** — when a simple bug is manually introduced into the source file, at
   least one generated test fails

Criterion 4 is the most important. Tests that run but don't catch bugs are worse than no tests.

---

## Context: Author and Company

- The author is a software developer at **Roster-5 Software**, a small (~11 person) veteran-owned
  company in Louisville, CO specializing in workforce management, scheduling, data analytics, and
  government/enterprise software (Java, C++, Oracle, AWS).
- AI adoption is growing at the company but the author is an early adopter. This project (and
  the ones that follow) are intended to build enough hands-on experience to consult the company
  on where AI can meaningfully advance software development.
- Future projects will likely be more domain-relevant to Roster5 (scheduling, optimization,
  analytics). This first project is intentionally general-purpose.

---

## Tech Stack Direction (to be confirmed in Research/PRD)

- **Language**: Python (author's strongest language)
- **AI**: Claude API (via Anthropic Python SDK) — already covered by Claude Max plan
- **Test framework target**: pytest
- **Interface**: CLI first; simple web UI is a stretch goal
- **No database required** — stateless tool, input file in, test file out

---

## Open Questions for the Idea Stage

- Should the tool handle a single file, or should it be able to traverse a directory/module?
- Should it output one test file or one test file per source file?
- Should it attempt to infer and mock external dependencies (e.g., database calls, HTTP
  requests), or stay focused on pure functions first?
- Should the tool provide any feedback to the user about what it generated and why, or just
  produce the file silently?
- What should happen when the Claude API returns something that isn't valid Python?
