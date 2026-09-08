---
name: project-start
description: Begin working with a project's existing Markdown notes, refine the initial design, and establish ongoing documentation. Use at the beginning of a project.
---

# Start project work

1. Find the notes folder from the user's message or the codebase's CLAUDE.local.md. Paths in that file are relative to the file; paths supplied in a command are relative to the working directory. Ask if the location is missing or conflicts with an existing project. If access is needed, ask the user to use `/add-dir` for that folder.
2. Read the codebase's instructions and the notes folder's CLAUDE.md. If the notes or their instructions are missing, explain what is missing and ask how to proceed. Do not silently create a different notes folder or overwrite existing notes.
3. Read the initial design and any existing requirements/tasks. Inspect Git status and the relevant source and tests; keep exploration focused. Record the actual codebase and notes paths in progress.md. For an empty project, say that implementation has not begun.
4. Explain your understanding and the important open questions. Help refine the design with the user. When asked to plan, turn agreed behavior into requirements and tasks with completion conditions and dependencies, following the notes instructions.
5. Continue with the requested work. Starting the workflow alone does not mean implementing the application. Keep the notes current automatically as work progresses, including decisions, task changes, failures, and verification results.
