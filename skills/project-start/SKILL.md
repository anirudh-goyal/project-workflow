---
name: project-start
description: Initialize or adopt a project's Markdown documentation workspace when the user starts the project workflow or supplies a notes directory. Preserve existing notes and establish context before implementation.
---

# Start a project workspace

1. Follow [context resolution](references/context.md). An explicit notes path is input, not authorization to overwrite documents or change an existing project binding.
2. Inspect existing project instructions, Git status when available, and existing notes. Read any notes CLAUDE.md before modifying that workspace.
3. For a new notes folder, use [the note templates](assets/notes/CLAUDE.md) and the six sibling Markdown files in that directory. Create only missing files; retain user content and customized rules. For existing notes, adopt their structure and reconcile missing pieces without reorganizing unprompted.
4. Record absolute codebase and notes paths in progress.md's current-state section. If a persistent binding is missing, add the Project documentation workflow section to the codebase's CLAUDE.local.md, preserving other content. State which path was saved. Ensure local-only configuration is excluded from Git via the local exclude file when a repository exists; never commit as part of initialization.
5. Read the supplied design/prompt and inspect only the relevant code path, tests, and development instructions. Discover actual run commands; label commands not yet run as unverified. For an empty codebase, record that no implementation exists.
6. Populate only evidence-backed context, supplied requirements, and useful open questions. Distinguish a user proposal from an adopted design. Do not invent requirements to fill templates.
7. Explain the current understanding, material questions, and a recommended next step briefly. Initialization alone does not authorize implementation. If the user also requested implementation, continue within that scope after resolving consequential uncertainty.

The notes CLAUDE.md governs ongoing updates after initialization. Do not require a checkpoint command for maintenance. This skill and its sibling skills should be installed together; copied assets remain part of this skill.
