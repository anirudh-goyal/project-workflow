# Requirements

Record desired behavior and observable acceptance criteria. Keep confirmation separate from delivery status; see [[CLAUDE]].

| ID  | Requirement | Acceptance criteria | Source / confirmation | Delivery status | Evidence |
| --- | ----------- | ------------------- | --------------------- | --------------- | -------- |

## Scope and non-goals

## Open questions

## Changed or withdrawn requirements

Retain the reason and source when scope changes.

## Example — illustrative only

This fictional customer-import example demonstrates the format. It is not a project requirement, decision, implementation, or verification result. Keep examples separate from live entries; do not copy their IDs or results into project state.

| ID | Requirement | Acceptance criteria | Source / confirmation | Delivery status | Evidence |
| --- | --- | --- | --- | --- | --- |
| R-EXAMPLE-001 | Detect missing required CSV headers. | The parser raises `MissingColumnError` naming `email` when that header is absent. | Agreed design; confirmed | verified | Four parser unit tests passed; see the example in [[progress]]. |
| R-EXAMPLE-002 | Reject invalid uploads before writing customers. | Return HTTP 400 naming the missing column; create no customers. | User discussion; confirmed | not_started | Endpoint integration is not implemented or verified. |

**Scope:** Validate the required header before importing rows. Email deliverability checks are outside the current scope.

**Open question:** Should `Email` and `EMAIL` be accepted as equivalent header names?
