---
name: project-resume
description: Review project notes and code in a fresh session, then summarize progress and possible next steps for the user to choose.
---

# Resume project work

1. Find the notes folder in the user's request or CLAUDE.local.md. A path in that file is relative to the file; a supplied path is relative to the working directory. Ask about missing or conflicting locations. Use `/add-dir` when access is needed.
2. Read the project instructions and the notes folder's CLAUDE.md. Read current progress, active requirements/tasks, and relevant design, decisions, and architecture. If expected notes are missing, tell the user.
3. Check the relevant code and tests, recent commits, and uncommitted changes. Confirm that the notes describe this codebase. Read older history only as needed.
4. Correct clearly outdated notes; ask when intent is uncertain. Preserve existing work. Past passing tests do not verify subsequent code changes.
5. Summarize what has been done so far, what works, and outstanding issues. Suggest reasonable next steps with brief reasons. Stop and wait for the user to choose what to work on; do not start or continue implementation.
