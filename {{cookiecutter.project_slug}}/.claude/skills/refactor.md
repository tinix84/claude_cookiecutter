# Skill: Refactor Code

## Description

Automatically invoked when the user asks to refactor, clean up, simplify, or improve code quality
without changing its external behavior. Also triggers when code smells are identified (long
functions, deep nesting, duplicated logic, magic numbers).

## Instructions

1. Read the target code and identify the specific smells or issues.
2. Confirm existing tests pass before starting (`{{cookiecutter.package_manager}} run test`).
3. Apply the refactoring in small, reversible steps:
   - Extract functions/methods for repeated logic.
   - Replace magic numbers with named constants.
   - Flatten deeply nested conditionals (early returns, guard clauses).
   - Remove dead code.
4. After each step, verify tests still pass.
5. Follow `.claude/rules/code-style.md` throughout.
6. Present a summary of changes and the rationale for each.

**Do not change external behavior.** If you discover a bug while refactoring, flag it separately
rather than fixing it inline.
