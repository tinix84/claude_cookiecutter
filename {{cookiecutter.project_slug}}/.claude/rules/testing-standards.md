# Testing Standards

These rules apply to all test files (`tests/`, `**/*.test.*`, `**/*_test.*`).

## Test Structure

- Each test file mirrors the source file it covers: `src/auth.py` → `tests/test_auth.py`.
- Group related tests in a class or `describe` block named after the unit under test.
- Follow **Arrange / Act / Assert** (AAA) structure within every test.

## Naming

- Test function names must describe the scenario: `test_login_fails_with_invalid_password`.
- Avoid generic names like `test_1`, `test_it`, or `test_works`.

## Coverage

- Minimum coverage threshold: **80%** for all new code.
- Critical paths (auth, payments, data mutations) require **100%** branch coverage.
- Run coverage before every PR: `{{cookiecutter.package_manager}} run test:coverage`.

## Test Types

| Type | Location | Purpose |
|------|----------|---------|
| Unit | next to source | test single functions/classes in isolation |
| Integration | `tests/integration/` | test multiple modules working together |
| E2E | `tests/e2e/` | test full user flows against a running server |

## Mocking

- Mock external services (HTTP, databases, file system) in unit tests.
- Use real services in integration tests against a local test environment.
- Never mock the system under test itself.

## Prohibited Patterns

- No `time.sleep` / `setTimeout` in tests; use deterministic mocks.
- No tests that depend on execution order; each test must be fully independent.
- No hardcoded ports or file paths; use fixtures/helpers.
