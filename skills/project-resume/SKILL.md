---
name: project-resume
description: Continue documented project work in a fresh session by reading its notes and checking the actual code and working tree.
---

# Resume project work

1. Find the notes folder from the user's message or the codebase's CLAUDE.local.md. Paths in that file are relative to the file; paths supplied in a command are relative to the working directory. Ask about a missing or conflicting location. If access is needed, ask the user to use `/add-dir` for that folder.
2. Read the codebase's instructions and the notes folder's CLAUDE.md. Read progress.md's current state, active requirements/tasks, and relevant design, decisions, and architecture. Read older history only when needed. If expected notes are missing, explain what is missing instead of creating a replacement.
3. Check the actual repository: branch, recent commits, tracked and untracked changes, and relevant source/tests. Without Git, inspect the files directly. Confirm these notes describe the current codebase.
4. Reconcile clear discrepancies in the notes; ask when intent is uncertain. Preserve existing work. Past passing checks are historical evidence, not proof that later changes work. Record unfinished or unverified behavior honestly.
5. Briefly explain the current goal, what works, outstanding issues, and the next action. Continue a clearly requested task, or finish the briefing if no implementation was requested.

Keep notes updated throughout subsequent work according to their CLAUDE.md. Do not wait for a checkpoint command or session end. Reading summaries alone does not establish that the code is correct or complete.
