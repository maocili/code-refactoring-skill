# code-refactoring skill

Practical, language-agnostic guidance for behavior-preserving refactoring in existing codebases.

## What this skill does

This skill helps you run refactoring as a safe, incremental workflow instead of a large rewrite. It is designed for situations where code is hard to change and you need confidence while improving structure.

Use it to:

- Identify high-impact smells and change-friction points.
- Choose the smallest safe first refactor.
- Apply micro-steps with immediate testing feedback.
- Keep changes behavior-preserving and review-friendly.
- Commit each completed refactor with a consistent message format.

## Core workflow

For each refactor, run this loop:

1. Apply one micro-step.
2. Run relevant tests immediately.
3. Repeat until one complete refactor reaches its structural goal.
4. Run refactor-level validation before commit.
5. Commit exactly one completed refactor using `[refactor]: xxx`.

Example commit messages:

- `[refactor]: extract pricing calculator`
- `[refactor]: rename payment state mapper`

## Install

Install from this repository with `skill-installer`:

```bash
skill-installer install git@github.com:maocili/code-refactoring-skill.git
```

## How to use

Call the skill in your Codex prompt:

- `$code-refactoring`

Typical requests:

- Plan a safe first refactor for a long function.
- Map observed smells to minimal refactoring moves.
- Execute test-first, behavior-preserving cleanup in small commits.

## Repository structure

- `SKILL.md`: Primary skill definition and operating workflow.
- `references/`: Execution checklists and refactoring selection guides.
- `agents/openai.yaml`: Agent metadata and default prompt wiring.
