---
applyTo: "backend/**/*,*.py"
---

# Backend-Specific Guidelines

## API Design
- Prefer explicit, versioned endpoints (for example: `/api/v1/...`).
- Use consistent request/response shapes and standard HTTP status codes.
- Validate all incoming input at the API boundary.
- All API endpoints must be defined in the `routers` folder.

## Security
- Never trust client input; sanitize and validate server-side.
- Enforce authentication and authorization on every protected endpoint.
- Avoid leaking sensitive data in errors, logs, or responses.

## Data & Persistence
- Use migrations for schema changes; do not modify production schemas manually.
- Keep queries parameterized to prevent SQL injection.
- Wrap multi-step writes in transactions when consistency is required.
- Load example database content from the `database.py` file.

## Error Handling & Logging
- Return actionable, non-sensitive error messages to clients.
- Log errors with context (request id, user id where applicable).
- Use structured logs and consistent log levels.
- Error handling is only logged on the server. Do not propagate to the frontend.

## Performance & Reliability
- Add pagination for list endpoints.
- Set sensible timeouts/retries for external service calls.
- Use idempotency keys for retry-safe write operations where applicable.

## Testing
- Add unit tests for business logic.
- Add integration tests for critical API flows.
- Cover validation, auth, and failure paths.

## Observability
- Emit metrics for request rate, latency, errors, and dependency failures.
- Add tracing across service boundaries when available.
- Define alerts for SLO-impacting conditions.

## Documentation
- Keep API docs up to date with endpoint/contract changes.
- Document environment variables and operational runbooks.
- Ensure all APIs are explained in the documentation.
- Verify changes in the backend are reflected in the frontend (`src/static/**`). If possible breaking changes are found, mention them to the developer.
