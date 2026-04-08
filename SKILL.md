---
name: code-refactoring
description: Practical, language-agnostic guidance for behavior-preserving refactoring in existing codebases. Use when identifying code smells, planning incremental cleanup, selecting a safe first refactoring, or executing test-first refactor steps for legacy or hard-to-change code.
---

# Code Refactoring

## Overview

Use this skill to plan and execute small, safe refactors inspired by Fowler-style practice. Keep changes behavior-preserving, test-first, and incremental so each step is understandable, reversible, and easy to validate.

## Refactoring Workflow

1. Define the target behavior and lock it with self-checking tests before changing structure.
2. Select one smell or pain point that blocks changeability now.
3. Choose the smallest safe refactoring that improves that exact pain point.
4. Apply one micro-step, then run the relevant tests immediately.
5. Commit only coherent structural changes with clear intent in the message.
6. Repeat until the code becomes easy enough for the feature or bug-fix change.
7. Stop when further cleanup gives low value compared with delivery needs.

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
- Maintain a rollback path through frequent commits and narrow scope.
- Avoid large-batch rewrites that hide intent or complicate review.
- Prefer deterministic transformations over stylistic churn.

## When to Load References

- Load [workflow-and-checklists.md](references/workflow-and-checklists.md) when planning execution order, verification cadence, or stop criteria.
- Load [smell-to-refactoring-map.md](references/smell-to-refactoring-map.md) when mapping observed smells to the smallest safe first move and follow-up move.
- Load [refactoring-catalog-quick-index.md](references/refactoring-catalog-quick-index.md) when selecting among chapter families or checking alternate refactoring options.

Focus on practical execution, not exhaustive catalog reproduction.
