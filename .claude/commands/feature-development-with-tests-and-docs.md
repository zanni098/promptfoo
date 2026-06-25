---
name: feature-development-with-tests-and-docs
description: Workflow command scaffold for feature-development-with-tests-and-docs in promptfoo.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-with-tests-and-docs

Use this workflow when working on **feature-development-with-tests-and-docs** in `promptfoo`.

## Goal

Implements a new feature, adds or modifies tests, and updates documentation.

## Common Files

- `src/commands/*.ts`
- `src/providers/**/*.ts`
- `test/**/*.test.ts`
- `site/docs/**/*.md`
- `site/static/config-schema.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement feature in src/
- Add or update tests in test/
- Update or add documentation in site/docs/ or site/static/

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.