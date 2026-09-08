---
name: project-resume
description: Recover a project's working context in a fresh coding-agent session using its notes and actual repository state. Use to resume documented work or recover after context loss.
---

# Resume project work

1. Follow [context resolution](../project-start/references/context.md), including reading the notes CLAUDE.md. Do not initialize a replacement workspace when expected notes are missing.
2. Read progress.md's current state and recent entries, active requirements/tasks, relevant design, adopted decisions, and technical architecture. Read older history only when needed to resolve a question.
3. Inspect the actual codebase: current branch/HEAD, tracked and untracked changes, and relevant source/test files. With no Git repository, inspect files directly and state that Git history is unavailable.
4. Compare the notes with current implementation and test evidence. A past passing result is historical evidence; relevant subsequent changes can invalidate it. Mark affected criteria unverified until checked. Do not reset status blindly or repair code during context recovery without task authorization.
5. Surface material contradictions, unexpected changes, or a different checkout. Preserve user work. Reconcile notes when the evidence is clear; ask when intent is ambiguous.
6. Give a concise briefing: current goal/task, implemented and verified behavior, outstanding uncertainty/blockers, and the next bounded action. Reference the critical files and symbols.
7. Resume implementation when requested or when continuing a clearly authorized task. Otherwise finish the briefing without inventing a task. Maintain notes automatically throughout subsequent work.

Recovery should establish useful working knowledge, not attempt an exhaustive repository survey. Do not claim expertise or completion merely from reading summaries.
