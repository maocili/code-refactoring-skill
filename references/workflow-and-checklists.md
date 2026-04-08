# Workflow And Checklists

Use this guide to run refactoring as a controlled loop instead of a big rewrite.

## Pre-Flight Checklist

- Confirm current behavior with self-checking tests.
- Define the exact scope of this refactoring pass.
- Identify one primary smell or change-friction point.
- Capture a rollback path through branch safety or recent commit boundaries.
- Align on non-goals for this pass to prevent scope creep.

## Execution Checklist

- Apply the smallest behavior-preserving step possible.
- Run targeted tests immediately after each micro-step.
- Repeat micro-step + test until one complete refactor reaches its structural goal.
- Run refactor-level tests before commit (at least targeted coverage for impacted code; include broader regression when available).
- Commit immediately after refactor-level tests pass.
- Keep each commit limited to one completed refactor; never batch multiple completed refactors together.
- Use commit message format `[refactor]: xxx` (for example, `[refactor]: extract pricing calculator`).
- Prefer renaming, extraction, and encapsulation before architecture-heavy changes.
- Remove duplication and ambiguity before introducing new abstractions.
- Pause if tests become flaky; stabilize feedback before proceeding.

## Stop And Exit Criteria

- Stop when the original obstacle to safe change is gone.
- Stop when additional cleanup yields little risk reduction.
- Stop when the next move requires feature-level decisions instead of structure changes.
- Exit with tests green and a concise summary of what changed and why.
- Leave clear handoff notes if additional refactoring remains.
