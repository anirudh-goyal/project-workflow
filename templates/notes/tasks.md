# Tasks

Use stable IDs, linked requirements, and concrete completion conditions. Status meanings are in [[CLAUDE]].

## Tasks

Use one heading per task, with its stable ID and a short description. Copy this structure for each entry; use labeled bullets rather than tables so text wraps naturally in Obsidian.

### T-001 — [Task description]

- **Status:** todo
- **Requirements:** [Related R- IDs.]
- **Dependencies:** [Related T- IDs, or None.]
- **Completion condition:** [Observable result needed to finish the task.]
- **Evidence / next action:** [Completion evidence or the concrete next step.]

## Blockers

Record the blocker and next action.

## Deferred work

Record why and whose scope decision this was.

## Example (fictional)

### T-EXAMPLE-001 — Add CSV header validation

- **Status:** done
- **Requirements:** R-EXAMPLE-001
- **Dependencies:** None
- **Completion condition:** Parser detects a missing email column; unit tests pass; notes reflect the change.
- **Evidence / next action:** Four parser tests passed; see the example entry in [[progress]].

### T-EXAMPLE-002 — Connect validation to the upload endpoint

- **Status:** todo
- **Requirements:** R-EXAMPLE-002
- **Dependencies:** T-EXAMPLE-001
- **Completion condition:** Missing header produces HTTP 400 and no customer writes; integration test passes.
- **Evidence / next action:** Next: inspect the endpoint's existing error handling.

### Example blockers

**Blockers:** None.
