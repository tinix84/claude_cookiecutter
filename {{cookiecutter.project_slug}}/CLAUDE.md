# {{cookiecutter.project_name}}

{{cookiecutter.project_description}}

## Project Overview

- **Author**: {{cookiecutter.author_name}} <{{cookiecutter.author_email}}>
- **Version**: {{cookiecutter.version}}
- **Primary Language**: {{cookiecutter.primary_language}}

## Build & Run Commands

<!-- Fill in your actual build, test, and run commands below -->

```bash
# Install dependencies
# e.g. npm install / pip install -r requirements.txt / cargo build

# Run tests
# e.g. npm test / pytest / cargo test

# Start the development server / run the project
# e.g. npm run dev / python main.py / cargo run

# Lint
# e.g. npm run lint / ruff check . / cargo clippy
```

## Architecture

<!-- Describe the high-level architecture of this project -->

- `src/` – main source code
- `tests/` – test suite
- `docs/` – documentation

## Key Conventions

- Follow the language/framework idioms used throughout the codebase.
- Keep functions small and single-purpose.
- All public functions and modules must have docstrings / JSDoc comments.
- Prefer explicit over implicit; avoid magic values — use named constants.
- Commits follow Conventional Commits: `feat:`, `fix:`, `chore:`, `docs:`, etc.

## Coding Standards

- Maximum line length: 100 characters.
- Use 4-space indentation (Python/Rust/Go) or 2-space (TypeScript/JavaScript).
- No trailing whitespace. Files must end with a newline.
- Imports are sorted: standard library → third-party → local.

## Testing Standards

- Every new feature must ship with tests.
- Unit tests live next to source files (`*.test.ts`, `test_*.py`, `*_test.go`).
- Integration tests live in `tests/integration/`.
- Minimum coverage threshold: 80%.

## API Conventions

- REST endpoints follow `/{resource}/{id}` naming (plural nouns, no verbs).
- HTTP status codes: 200 OK, 201 Created, 400 Bad Request, 404 Not Found, 500 Internal Server Error.
- All API responses return JSON with a consistent envelope: `{ "data": ..., "error": null }`.
- Validate all inputs before processing; never trust external data.

## Gotchas & Known Pitfalls

<!-- Document project-specific surprises here -->

- <!-- e.g. "The `foo` module has a global singleton; do not instantiate it twice." -->
- <!-- e.g. "Environment variables must be set before importing `config.py`." -->

## Environment Variables

<!-- List required environment variables -->

| Variable | Required | Description |
|----------|----------|-------------|
| `APP_ENV` | Yes | `development`, `staging`, or `production` |

## Related Documentation

- [Project Docs](./docs/)
- [Claude Code Docs](https://docs.anthropic.com/en/docs/claude-code)
