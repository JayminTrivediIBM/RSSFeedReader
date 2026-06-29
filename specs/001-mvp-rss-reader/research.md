# Research: MVP RSS Reader

## Decision

Use a simple backend API endpoint for adding and listing subscriptions and a Blazor page for entering a URL and displaying the current subscription list.

## Rationale

This approach aligns with the stakeholder goals for a minimal proof-of-concept and with the project’s chosen ASP.NET Core + Blazor architecture. It keeps the implementation focused on the MVP while leaving room to add feed fetching and persistence later.

## Alternatives considered

- Full feed parsing and item display in the MVP: rejected because it expands scope beyond the stated goals.
- Client-only storage with no API: rejected because the architecture and project notes indicate a backend/frontend split for future maintainability.
- Database-backed persistence in the MVP: rejected because the MVP explicitly calls for in-memory storage and simple implementation.
