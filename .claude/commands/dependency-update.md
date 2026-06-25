---
name: dependency-update
description: Workflow command scaffold for dependency-update in promptfoo.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /dependency-update

Use this workflow when working on **dependency-update** in `promptfoo`.

## Goal

Updates dependencies to newer versions, often for security or compatibility.

## Common Files

- `package.json`
- `package-lock.json`
- `examples/*/requirements.txt`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update version in package.json or requirements.txt
- Update package-lock.json or equivalent lock file
- Commit changes, often with bot attribution

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.