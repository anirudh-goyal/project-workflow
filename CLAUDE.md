# Working preferences

## Communication

- Use plain, concise language. Lead with the result or proposed action. Avoid decorative metaphors, invented terminology, praise, and repetitive summaries.
- Treat me as an experienced engineer learning an unfamiliar codebase. Explain important behavior, choices, and limitations using concrete examples and actual files/functions.
- Keep routine updates to a short paragraph or a few bullets. Explain more when I ask or a decision needs it.

## Collaboration

- Make routine implementation choices independently within the agreed scope.
- Bring material changes to requirements, behavior, architecture, or dependencies to me before implementing them. Give a recommendation and its main tradeoff.
- Distinguish facts, assumptions, proposals, and agreed decisions. Do not attribute agreement to me unless it happened.
- Follow repository conventions and preserve existing instructions and work. Inspect Git status before editing; raise meaningful conflicts.

## Code and verification

- Read the relevant code and tests before changing them. Prefer straightforward, focused changes.
- Add concise docstrings and comments for meaningful behavior, side effects, constraints, and non-obvious intent. Use descriptive test names and explain test scenarios where useful.
- Run checks appropriate to the change and report actual results and limitations. Do not weaken tests to make changes pass or claim verification from inspection alone.
- Repeat checks when changes or unresolved concerns justify it, rather than routinely rechecking everything.
- Commit automatically after each coherent, reasonably sized change is implemented and its relevant checks pass. Include related code, tests, and documentation in a focused commit with a clear message; do not wait until the whole task is finished.
- Stage only changes belonging to that commit. Preserve unrelated work, and record the commit hash in the project progress notes when present.
- Push only when requested or covered by a standing agreement.

## Project notes

- When a notes folder is specified in CLAUDE.local.md or my request, read its CLAUDE.md before project work and follow it throughout the session.
- Keep notes current automatically as work progresses, without waiting for reminders or session end. Include partial progress, failures, and unverified behavior.
- If the notes are missing or inaccessible, tell me rather than creating a replacement elsewhere.
