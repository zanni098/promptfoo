```markdown
# promptfoo Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute effectively to the `promptfoo` codebase, a TypeScript project using React. You'll learn the project's coding conventions, commit patterns, and the main development workflows, including dependency updates, feature development, bugfixing, releases, and more. This guide will help you write code, tests, and documentation that fit seamlessly into the repository.

---

## Coding Conventions

- **Language:** TypeScript
- **Framework:** React
- **File Naming:** Use `camelCase` for file and directory names.
  - Example: `myComponent.ts`, `providerUtils.ts`
- **Import Style:** Use relative imports.
  - Example:
    ```typescript
    import { runTests } from './testRunner';
    ```
- **Export Style:** Use named exports.
  - Example:
    ```typescript
    export function evaluatePrompt() { ... }
    export const DEFAULT_CONFIG = { ... };
    ```
- **Commit Messages:** Follow [Conventional Commits](https://www.conventionalcommits.org/) with these prefixes:
  - `fix`, `chore`, `feat`, `docs`, `test`
  - Example: `feat: add new OpenAI provider integration`

---

## Workflows

### Dependency Update
**Trigger:** When a dependency has a new release or a security update is available.  
**Command:** `/update-dependency`

1. Update the version in `package.json` or `examples/*/requirements.txt`.
2. Run your package manager to update `package-lock.json` or equivalent lock file.
3. Commit the changes, often with bot attribution.

**Example:**
```sh
npm install some-package@latest
git add package.json package-lock.json
git commit -m "chore: update some-package to latest version"
```

---

### Feature Development with Tests and Docs
**Trigger:** When adding a new CLI command, provider, or major feature.  
**Command:** `/new-feature`

1. Implement the feature in `src/` (e.g., `src/commands/newCommand.ts`).
2. Add or update tests in `test/` (e.g., `test/commands/newCommand.test.ts`).
3. Update or add documentation in `site/docs/` or `site/static/`.

**Example:**
```typescript
// src/commands/newCommand.ts
export function newCommand() { ... }
```
```typescript
// test/commands/newCommand.test.ts
import { newCommand } from '../../src/commands/newCommand';

test('newCommand works', () => {
  expect(newCommand()).toBeTruthy();
});
```

---

### Bugfix with Corresponding Tests
**Trigger:** When a bug is found in the codebase.  
**Command:** `/bugfix`

1. Fix the bug in the relevant `src/` code file.
2. Add or update a test in `test/` to cover the bug or regression.
3. Optionally update related documentation.

**Example:**
```typescript
// src/utils/calc.ts
export function add(a: number, b: number) {
  return a + b; // Fixed off-by-one error
}
```
```typescript
// test/utils/calc.test.ts
import { add } from '../../src/utils/calc';

test('add returns correct sum', () => {
  expect(add(2, 2)).toBe(4);
});
```

---

### Release Version Bump
**Trigger:** When preparing for a new release.  
**Command:** `/release`

1. Update the version in `package.json`.
2. Update `package-lock.json`.
3. Update `CHANGELOG.md` with release notes.
4. Update `.release-please-manifest.json`.

**Example:**
```sh
npm version minor
git add package.json package-lock.json CHANGELOG.md .release-please-manifest.json
git commit -m "chore(release): v1.2.0"
```

---

### Code Scan Action Update
**Trigger:** When improving or bugfixing the code-scan-action workflow.  
**Command:** `/update-code-scan-action`

1. Modify `code-scan-action/src/main.ts`.
2. Update or add tests in `test/code-scan-action/main.test.ts`.

**Example:**
```typescript
// code-scan-action/src/main.ts
export function scanCode() { ... }
```
```typescript
// test/code-scan-action/main.test.ts
import { scanCode } from '../../code-scan-action/src/main';

test('scanCode detects issues', () => {
  expect(scanCode('bad code')).toContain('error');
});
```

---

### Provider Enhancement with Tests
**Trigger:** When adding features or fixing bugs in provider integrations.  
**Command:** `/update-provider`

1. Update provider logic in `src/providers/`.
2. Update or add tests in `test/providers/`.

**Example:**
```typescript
// src/providers/myProvider.ts
export function enhancedProvider() { ... }
```
```typescript
// test/providers/myProvider.test.ts
import { enhancedProvider } from '../../src/providers/myProvider';

test('enhancedProvider returns expected result', () => {
  expect(enhancedProvider()).toBeDefined();
});
```

---

## Testing Patterns

- **Framework:** [vitest](https://vitest.dev/)
- **Test File Pattern:** `*.test.ts`
- **Test Structure:** Place tests in the `test/` directory, mirroring the source structure.

**Example:**
```typescript
// test/utils/math.test.ts
import { add } from '../../src/utils/math';

test('add adds numbers', () => {
  expect(add(1, 2)).toBe(3);
});
```

---

## Commands

| Command                     | Purpose                                                      |
|-----------------------------|--------------------------------------------------------------|
| /update-dependency          | Update dependencies to newer versions                        |
| /new-feature                | Start a new feature with tests and documentation             |
| /bugfix                     | Fix a bug and add/update corresponding tests                 |
| /release                    | Bump project version and update changelogs                   |
| /update-code-scan-action    | Update or fix the code-scan GitHub Action and its tests      |
| /update-provider            | Enhance or fix provider logic and ensure test coverage        |
```
