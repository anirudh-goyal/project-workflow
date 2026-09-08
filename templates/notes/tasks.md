# Tasks

Use stable IDs, linked requirements, and concrete completion conditions. Status meanings are in [[CLAUDE]].

| ID | Task | Requirements | Dependencies | Status | Completion condition | Evidence / next action |
| --- | --- | --- | --- | --- | --- | --- |

## Blockers

Record the blocker and next action.

## Deferred work

Record why and whose scope decision this was.

## Example (fictional)

| ID            | Task                                       | Requirements  | Dependencies  | Status | Completion condition                                                              | Evidence / next action                                           |
| ------------- | ------------------------------------------ | ------------- | ------------- | ------ | --------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| T-EXAMPLE-001 | Add CSV header validation.                 | R-EXAMPLE-001 | None          | done   | Parser detects a missing email column; unit tests pass; notes reflect the change. | Four parser tests passed; see the example entry in [[progress]]. |
| T-EXAMPLE-002 | Connect validation to the upload endpoint. | R-EXAMPLE-002 | T-EXAMPLE-001 | todo   | Missing header produces HTTP 400 and no customer writes; integration test passes. | Next: inspect the endpoint's existing error handling.            |

**Blockers:** None.
