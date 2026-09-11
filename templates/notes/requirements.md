# Requirements

Record desired behavior and observable acceptance criteria. Keep confirmation separate from delivery status; see [[CLAUDE]].

## Requirements

Use one heading per requirement, with its stable ID and a short description. Copy this structure for each entry; use labeled bullets rather than tables so text wraps naturally in Obsidian.

### R-001 — [Desired behavior]

- **Acceptance criteria:** [Observable conditions that must hold.]
- **Source / confirmation:** [Source; proposed or confirmed.]
- **Delivery status:** not_started
- **Evidence:** [Verification results, or what remains unverified.]

## Scope and non-goals

## Open questions

## Changed or withdrawn requirements

Retain the reason and source when scope changes.

## Example (fictional)

### R-EXAMPLE-001 — Detect missing required CSV headers

- **Acceptance criteria:** The parser raises `MissingColumnError` naming `email` when that header is absent.
- **Source / confirmation:** Agreed design; confirmed.
- **Delivery status:** verified
- **Evidence:** Four parser unit tests passed; see the example in [[progress]].

### R-EXAMPLE-002 — Reject invalid uploads before writing customers

- **Acceptance criteria:** Return HTTP 400 naming the missing column; create no customers.
- **Source / confirmation:** User discussion; confirmed.
- **Delivery status:** not_started
- **Evidence:** Endpoint integration is not implemented or verified.

### Example scope and open questions

**Scope:** Validate the required header before importing rows. Email deliverability checks are outside the current scope.

**Open question:** Should `Email` and `EMAIL` be accepted as equivalent header names?
