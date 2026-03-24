# Skill: Write Tests

## Description

Automatically invoked when the user asks to write, add, generate, or create tests for a function,
module, class, or feature. Also triggers when a test file is opened or a new source file is
created without a corresponding test file.

## Instructions

1. Identify the unit under test from the conversation or the file currently being edited.
2. Read the source file to understand the public interface, edge cases, and error paths.
3. Check `.claude/rules/testing-standards.md` for project-specific requirements.
4. Write tests that:
   - Follow the **Arrange / Act / Assert** pattern.
   - Cover the happy path, edge cases, and error conditions.
   - Use the mocking strategy defined in the testing standards.
   - Are placed in the correct location (next to source for unit tests, `tests/integration/` for integration tests).
5. Run the tests to confirm they pass before presenting them to the user.
