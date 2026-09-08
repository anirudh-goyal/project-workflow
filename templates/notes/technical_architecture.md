# Technical architecture

Describe the actual implementation with links to files and functions. Proposed behavior belongs in [[design]].

## System purpose and boundaries

## Concrete execution path

## Components and source references

| Component | Responsibility | File and symbol | Existing or changed |
| --- | --- | --- | --- |

## State, interfaces, and failure behavior

## Development and verification commands

Label commands unverified until actually executed. Link results from [[progress]].

## Implemented changes and current limitations

## Example (fictional)

**Existing system:** The upload endpoint in `src/api/imports.py`, function `upload_customers()`, reads a CSV and writes customer records.

**Implemented change:** `src/imports/csv_reader.py`, function `validate_headers()`, checks for the `email` column and raises `MissingColumnError` when it is absent. The parser's unit tests cover this behavior.

**Current limitation:** The endpoint does not call the validator yet. HTTP 400 responses and preventing writes for invalid uploads are planned, not implemented. See T-EXAMPLE-002 in [[tasks]].

**Verification:** `pytest tests/imports/test_csv_reader.py -q` passed four tests in the example progress entry. This establishes parser behavior only; an integration test is still needed.

Code paths above are illustrative; use links to actual files in project entries.
