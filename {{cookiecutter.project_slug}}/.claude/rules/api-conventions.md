# API Conventions

These rules apply to all files under `src/api/`, `src/routes/`, and `**/*router*`.

## URL Structure

- Use **plural nouns** for resource names: `/users`, `/orders`, `/products`.
- Nest sub-resources: `/users/{id}/orders`.
- No verbs in URLs; use HTTP methods to express intent.
- Use `kebab-case` for multi-word segments: `/payment-methods`.

## HTTP Methods

| Method | Purpose | Success Code |
|--------|---------|--------------|
| GET | Retrieve resource(s) | 200 |
| POST | Create a new resource | 201 |
| PUT | Replace a resource | 200 |
| PATCH | Partial update | 200 |
| DELETE | Remove a resource | 204 |

## Response Envelope

All responses must use this JSON envelope:

```json
{
  "data": { ... },
  "error": null,
  "meta": {
    "page": 1,
    "per_page": 20,
    "total": 100
  }
}
```

Error responses:

```json
{
  "data": null,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Human-readable description",
    "details": [ ... ]
  }
}
```

## Versioning

- All routes are prefixed with `/api/v{N}`, e.g., `/api/v1/users`.
- Breaking changes require a new version; additive changes do not.

## Authentication

- Use Bearer token (`Authorization: Bearer <token>`) for all authenticated endpoints.
- Never pass credentials in query parameters.

## Input Validation

- Validate all inputs at the API boundary before calling business logic.
- Return `400 Bad Request` with field-level error details for validation failures.
- Sanitize inputs to prevent injection attacks.
