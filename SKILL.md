---
name: code-refactoring
description: Practical, language-agnostic guidance for behavior-preserving refactoring in existing codebases. Use when identifying code smells, planning incremental cleanup, selecting a safe first refactoring, or executing test-first refactor steps for legacy or hard-to-change code.
---

# Code Refactoring

## Overview

Use this skill to plan and execute small, safe refactors inspired by Fowler-style practice. Keep changes behavior-preserving, test-first, and incremental so each step is understandable, reversible, and easy to validate.

## Refactoring Workflow

Before entering the loop, lock current behavior with self-checking tests and choose one concrete smell to address.

Use this fixed loop for each refactor:

1. Apply one micro-step toward the active refactor.
2. Run relevant tests immediately after that micro-step.
3. Repeat steps 1-2 until one complete refactor reaches its structural goal.
4. Test the completed refactor before commit (at least targeted tests for affected code; include higher-level regression when available).
5. Commit exactly that one completed refactor with message format `[refactor]: xxx` (for example, `[refactor]: extract pricing calculator`, `[refactor]: rename payment state mapper`).

Do not batch multiple completed refactors into one commit. Start the loop again for the next refactor, and stop when further cleanup gives low value compared with delivery needs.

## Smell Triage

Prioritize smells that increase change risk or force repeated edits:

- Start with duplication, long functions, repeated conditionals, and unclear names.
- Prefer refactors that reduce future edits in multiple places.
- Defer broad architectural refactors unless simple moves cannot unblock progress.
- Escalate to heavier refactorings only after low-risk options stop helping.

## Choose the First Refactoring

Default to the simplest first move that clarifies intent without changing behavior:

- Improve names first with function/variable/field renaming.
- Extract small, intention-revealing functions before moving behavior.
- Encapsulate mutable or global data before wider structural changes.
- Replace repetitive branch logic with isolated helper functions before polymorphism.
- Move behavior closer to the data it uses when ownership is unclear.

Use this sequence unless the codebase constraints force a different order.

## Safety Guardrails

- Preserve behavior during refactor steps; avoid mixing refactoring with feature logic.
- Keep each step small enough to isolate regressions quickly.
- Run tests after every micro-change, not only at the end.
- Treat a refactor as complete only when its structural goal is done and refactor-level tests pass.
- Commit one completed refactor per commit; never combine multiple completed refactors.
- Use commit messages in the exact format `[refactor]: xxx`.
- Maintain a rollback path through frequent commits and narrow scope.
- Avoid large-batch rewrites that hide intent or complicate review.
- Prefer deterministic transformations over stylistic churn.

## When to Load References

- Load [workflow-and-checklists.md](references/workflow-and-checklists.md) when planning execution order, verification cadence, or stop criteria.
- Load [smell-to-refactoring-map.md](references/smell-to-refactoring-map.md) when mapping observed smells to the smallest safe first move and follow-up move.
- Load [refactoring-catalog-quick-index.md](references/refactoring-catalog-quick-index.md) when selecting among chapter families or checking alternate refactoring options.

Focus on practical execution, not exhaustive catalog reproduction.
