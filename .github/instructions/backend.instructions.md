# Backend-Specific Guidelines

## API Design
- Prefer explicit, versioned endpoints (for example: `/api/v1/...`).
- Use consistent request/response shapes and standard HTTP status codes.
- Validate all incoming input at the API boundary.

## Security
- Never trust client input; sanitize and validate server-side.
- Enforce authentication and authorization on every protected endpoint.
- Avoid leaking sensitive data in errors, logs, or responses.

## Data & Persistence
- Use migrations for schema changes; do not modify production schemas manually.
- Keep queries parameterized to prevent SQL injection.
- Wrap multi-step writes in transactions when consistency is required.

## Error Handling & Logging
- Return actionable, non-sensitive error messages to clients.
- Log errors with context (request id, user id where applicable).
- Use structured logs and consistent log levels.

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
