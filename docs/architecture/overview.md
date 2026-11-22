## Architectural Principals to Guide Design and Development

| Principle | Description |
|---|---|
| API-first | The REST API defines the application contract |
| Separation of concerns | Clients, business logic and persistence remain independent |
| Database integrity | PostgreSQL constraints enforce fundamental data integrity |
| Transactional correctness | Financial transactions are atomic and auditable |
| Deterministic accounting | Portfolio calculations are reproducible |
| Explicit contracts | API request and response structures are documented |
| Testability | Business logic can be tested independently of infrastructure |
| Extensibility | Future clients, including AI agents, can use the same API |