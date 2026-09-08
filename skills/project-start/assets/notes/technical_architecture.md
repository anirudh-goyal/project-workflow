# Technical architecture

Describe the current implementation, distinguishing existing code from changes made during this work. Proposed future behavior belongs in [[design]].

## System purpose and boundaries

Not yet inspected.

## Concrete execution path

## Components and source references

| Component | Responsibility | File and symbol | Existing or changed |
| --- | --- | --- | --- |

## State, interfaces, and failure behavior

## Development and verification commands

Label commands unverified until actually executed. Link results from [[progress]].

## Implemented changes and current limitations

## Example — illustrative only

This fictional customer-import example demonstrates the format. It is not a project requirement, decision, implementation, or verification result. Keep examples separate from live entries; do not copy their IDs or results into project state.

**Existing system:** The upload endpoint in `src/api/imports.py`, function `upload_customers()`, reads a CSV and writes customer records.

**Implemented change:** `src/imports/csv_reader.py`, function `validate_headers()`, checks for the `email` column and raises `MissingColumnError` when it is absent. The parser's unit tests cover this behavior.

**Current limitation:** The endpoint does not call the validator yet. HTTP 400 responses and preventing writes for invalid uploads are planned, not implemented. See T-EXAMPLE-002 in [[tasks]].

**Verification:** `pytest tests/imports/test_csv_reader.py -q` passed four tests in the example progress entry. This establishes parser behavior only; an integration test is still needed.

In a real project, turn these illustrative code paths into links to the actual files, retaining the function names.
