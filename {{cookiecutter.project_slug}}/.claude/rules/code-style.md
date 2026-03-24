# Code Style Rules

These rules apply to all source files in this project.

## Formatting

- Maximum line length: **100 characters**.
- Indentation: 4 spaces (Python / Rust / Go) | 2 spaces (TypeScript / JavaScript).
- Files must end with a single newline; no trailing whitespace on any line.
- Use double quotes for strings unless single quotes are idiomatic in the language.

## Naming Conventions

- **Variables / functions**: `snake_case` (Python/Rust/Go) | `camelCase` (TypeScript/JS).
- **Classes / types / interfaces**: `PascalCase` in all languages.
- **Constants**: `UPPER_SNAKE_CASE`.
- **File names**: `snake_case` (Python) | `kebab-case` (TypeScript/JS).

## Comments

- Write comments for **why**, not **what**.
- All public functions, classes, and modules require docstrings / JSDoc.
- TODO comments must include an assignee and ticket reference: `TODO(alice): #123 – fix edge case`.

## Imports

Order: standard library → third-party packages → local modules, separated by blank lines.

## Prohibited Patterns

- No magic numbers — use named constants.
- No bare `except` / `catch` without explicit error type.
- No `console.log` / `print` left in production code; use the project logger.
- No deeply nested callbacks; prefer async/await or promise chains.
