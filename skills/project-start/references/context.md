# Resolve the project context

1. Identify the codebase from the user's request or current working directory. Read applicable project instructions. Do not assume the workflow distribution repository is the target codebase.
2. Look for a `Project documentation workflow` section in the codebase's CLAUDE.local.md. Resolve its notes directory relative to that file, or use an absolute path as written. These are natural-language configuration conventions, not Claude Code variable interpolation.
3. An explicit notes path supplied by the user overrides the configured path for the invocation. Resolve explicit relative paths against the current working directory. If it conflicts with a saved binding, state the discrepancy and clarify before reassigning the persistent binding or writing to an unrelated workspace. With no path or binding, ask one focused question; do not guess which existing notes belong to this project.
4. Check that the directory is accessible. Naming a directory in Markdown does not grant filesystem access. In Claude Code, direct the user to `/add-dir <notes-directory>` when needed. Do not work around access restrictions.
5. Read `<notes-directory>/CLAUDE.md` explicitly. Additional-directory instructions are not automatically loaded by default. For a resume, missing workflow instructions require recovery or clarification; do not replace customized rules with a template silently.
6. Check the recorded codebase binding in progress.md if present. A different checkout or moved directory requires reconciliation against the user's intent and actual repository state before edits.
7. Read the note sections needed for the task and the actual source/test files they reference. Notes describe evidence; they do not override current code, test results, or direct user corrections. Explain material discrepancies and update notes accurately.

## Portable local binding

A codebase's CLAUDE.local.md can contain:

```markdown
# Project documentation workflow

The notes directory is `../notes`, relative to this file.
Before planning or implementing work, read that directory's CLAUDE.md
and follow its workflow throughout the session. Keep notes synchronized
automatically as work progresses, without waiting for reminders.
On a fresh session, use project-resume for existing work.
```

Preserve existing instructions when adding this section. Use one authoritative binding. Do not copy project-specific paths into global preferences.
