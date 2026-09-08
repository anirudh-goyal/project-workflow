# Tasks

Use stable IDs, linked requirements, and concrete completion conditions. Status meanings are in [[CLAUDE]].

| ID | Task | Requirements | Dependencies | Status | Completion condition | Evidence / next action |
| --- | --- | --- | --- | --- | --- | --- |

## Blockers

Record task, prior state, blocker, and unblocking action.

## Deferred work

Record why and whose scope decision this was.

## Example — illustrative only

This fictional customer-import example demonstrates the format. It is not a project requirement, decision, implementation, or verification result. Keep examples separate from live entries; do not copy their IDs or results into project state.

| ID | Task | Requirements | Dependencies | Status | Completion condition | Evidence / next action |
| --- | --- | --- | --- | --- | --- | --- |
| T-EXAMPLE-001 | Add CSV header validation. | R-EXAMPLE-001 | None | done | Parser detects a missing email column; unit tests pass; notes reflect the change. | Four parser tests passed; see the example entry in [[progress]]. |
| T-EXAMPLE-002 | Connect validation to the upload endpoint. | R-EXAMPLE-002 | T-EXAMPLE-001 | todo | Missing header produces HTTP 400 and no customer writes; integration test passes. | Next: inspect the endpoint's existing error handling. |

**Blockers:** None currently. Parser validation is complete, but R-EXAMPLE-002 remains outstanding until the endpoint behavior is implemented and tested.
