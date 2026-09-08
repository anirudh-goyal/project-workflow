# Technical architecture

This living document explains how our implementation works and how it fits into the relevant existing systems. Update it as we learn about the codebase and implement or change behavior. Include enough surrounding context to understand the interactions, with links to real files and functions. Describe what exists today; proposed behavior belongs in [[design]]. Organize the explanation in whatever way best fits the project.

## Running the code and tests

Record the setup, prerequisites, working directory, and commands needed to run the application and relevant tests. Mark commands unverified until executed; link results from [[progress]].

## Example (fictional)

**Existing system:** The upload endpoint in `src/api/imports.py`, function `upload_customers()`, reads a CSV and writes customer records.

**Implemented change:** `src/imports/csv_reader.py`, function `validate_headers()`, checks for the `email` column and raises `MissingColumnError` when it is absent. The parser's unit tests cover this behavior.

**Current limitation:** The endpoint does not call the validator yet. HTTP 400 responses and preventing writes for invalid uploads are planned, not implemented. See T-EXAMPLE-002 in [[tasks]].

**Verification:** `pytest tests/imports/test_csv_reader.py -q` passed four tests in the example progress entry. This establishes parser behavior only; an integration test is still needed.

Code paths above are illustrative; use links to actual files in project entries.
