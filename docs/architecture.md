# Architecture

## Boundaries

- `client/`: user interface, accessible interaction patterns, loading/error/empty states.
- `server/`: HTTP API, validation, business rules, and data access.
- `tests/`: repeatable accessibility, API, and integration checks.
- `docs/`: audit evidence, architecture decisions, and setup instructions.

Keep UI presentation out of server business logic. Keep persistence details behind server-side data-access functions. Share API contracts through documented request/response examples rather than importing server internals into the client.

## First vertical feature slice: service search

1. A user enters a keyword in a visibly labelled search field.
2. The client submits `GET /api/services?q=<keyword>`.
3. The server trims and validates the query, then returns a consistent JSON response.
4. The client announces the result count in a status region and displays results or a useful empty state.
5. Tests cover keyboard use, form labels, API validation, and empty/error states.

## Proposed API contract

`GET /api/services?q=water`

Successful response:
```json
{
  "items": [
    {
      "id": "sample-1",
      "title": "Example public service",
      "description": "Placeholder data for local development."
    }
  ],
  "total": 1
}
```

This is a proposed contract, not a live integration with the target government portal.
