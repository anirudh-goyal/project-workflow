# Project Workflow

My preferred way of working on software projects with coding agents: maintain context across sessions, make engineering decisions explicit, and stay informed as the implementation evolves.

The workflow combines concise working preferences, reusable Claude Code skills, and a local Markdown workspace that can be opened in Obsidian or any editor. The documents track intended behavior, current implementation, tasks, decisions, and verification evidence. Agents update them continuously during work, so a new session can recover context without relying on the previous conversation.

Setup uses normal Claude Code features and file operations. No setup scripts, launcher, plugin, external service, or Obsidian extension is required. The Markdown documents are useful with other coding agents too; installation and command examples here target Claude Code.

## Principles

- **Stay involved.** Agents explain consequential choices clearly and bring material scope or architecture decisions to me, while handling routine implementation details independently.
- **Keep context current.** Notes change when requirements, decisions, task state, implementation, and verification change—not only when a session ends.
- **Separate intent from evidence.** A proposed design is different from implemented architecture. Code that exists is different from behavior that has been verified.
- **Recover from the actual state.** A new session reads the notes and checks the relevant source, tests, and working tree before continuing.
- **Preserve existing work.** Setup adopts existing project instructions and notes instead of replacing them.

## What is included

| Path                                                              | Purpose                                                                             |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [CLAUDE.md](CLAUDE.md)                                            | General communication, collaboration, implementation, and documentation preferences |
| [templates/CLAUDE.local.md](templates/CLAUDE.local.md)            | Project-local binding to the notes directory                                        |
| [skills/project-start](skills/project-start/SKILL.md)             | Initialize or adopt a documentation workspace and establish project context         |
| [skills/project-plan](skills/project-plan/SKILL.md)               | Refine a design into requirements and executable tasks                              |
| [skills/project-resume](skills/project-resume/SKILL.md)           | Reconstruct working context in a fresh session                                      |
| [skills/project-walkthrough](skills/project-walkthrough/SKILL.md) | Explain the implementation, prepare a demo, or check understanding                  |
| [Note templates](skills/project-start/assets/notes/CLAUDE.md)     | The ongoing documentation rules and six starter documents                           |

Install the **four skill directories together, including their assets and references**. The skills share the context-resolution reference shipped inside `project-start`. Copying only the `SKILL.md` files will break the package.

## Quick setup with Claude

Clone this repository wherever you keep personal tools:

```bash
git clone https://github.com/anirudh-goyal/project-workflow.git
```

While this repository is private, GitHub access is required to clone it. The workflow itself needs no connection to this repository after installation.

Give Claude access to the downloaded repository and your target locations, then ask it to read this README. Use the real absolute paths on your machine in the following prompts.

### Existing codebase

Start Claude Code in the existing codebase. Add access to the downloaded workflow repository and the parent location where the notes folder will be created, using `/add-dir` if needed. Then send:

```text
Read /absolute/path/project-workflow/README.md and follow its
agent setup procedure to install my project workflow.

Existing codebase: /absolute/path/my-project
Notes directory: /absolute/path/my-project-notes
Installation scope: personal (~/.claude), with project-local fallback

Preserve existing instructions, skills, notes, and uncommitted work.
Set up the workflow and initialize the notes using supplied context.
Do not implement application changes or commit/push anything.
```

### New codebase

Start Claude Code in an accessible parent directory. Add access to the downloaded workflow repository and target parent directory if needed. Then send:

```text
Read /absolute/path/project-workflow/README.md and follow its
agent setup procedure for a new project.

New codebase: /absolute/path/my-new-project
Notes directory: /absolute/path/my-new-project-notes
Installation scope: personal (~/.claude), with project-local fallback

Create the codebase directory and initialize a local Git repository.
Set up the workflow and notes. Do not choose an application stack,
scaffold an application, or create commits or remotes yet.

Initial project idea: [describe the project, or say it is not yet defined]
```

If the requested new directory already contains work, Claude should adopt it as an existing codebase. Git initialization is optional; omit that sentence if you do not want a Git repository yet.

## Agent setup procedure

**Instructions for the agent performing installation:** treat the user's setup request as authorization for the requested local installation. Resolve the supplied paths and scope, preserve existing work, and complete the available setup without asking again about routine file operations. Ask only for genuinely missing information, material conflicts, or required access. Setup does not authorize application implementation, commits, pushes, or remote creation unless separately requested.

1. **Identify source and targets.** Read this repository's general preferences, local binding template, and skill files. Confirm the codebase and notes paths from the request. Never mistake the downloaded workflow repository for the target codebase. The notes folder should normally be a sibling of the codebase, outside this distribution repository.
2. **Inspect before writing.** Read target instructions and existing configuration, including global preferences if using personal scope. Inspect Git status when the target is a repository. Preserve modified/untracked files and existing note content. For an explicitly requested new project, create the directory and initialize Git only if requested; do not create a nested Git repository inside an existing target repository by accident.
3. **Install working preferences.** For personal scope, merge this repository's `CLAUDE.md` into `~/.claude/CLAUDE.md`. If the destination is absent, copy it. If it exists, add a clearly labeled `Project Workflow preferences` section containing missing compatible guidance; do not duplicate rules on repeated setup. Surface substantive conflicts rather than silently changing established preferences. Keep a local backup before modifying existing configuration; leave it outside tracked project content.
4. **Install all skills.** Copy the complete four directories from `skills/` into `~/.claude/skills/`. Reuse identical installations. If a same-named skill differs, inspect it and preserve customizations; do not blindly overwrite it. When global installation is unavailable or the user selects project scope, install under `<codebase>/.claude/skills/` and merge the general preferences into `<codebase>/CLAUDE.local.md` instead. Never replace the codebase's shared `CLAUDE.md`.
5. **Bind the notes directory.** Merge the section from `templates/CLAUDE.local.md` into `<codebase>/CLAUDE.local.md`. Replace its example directory with the actual path, preferably relative to that file. Preserve unrelated sections. Reuse an identical binding; ask before replacing a different existing project binding. This is a convention interpreted by the skills, not an environment variable or automatic path expansion.
6. **Create or adopt notes.** Copy only missing files from `skills/project-start/assets/notes/` into the chosen notes directory, including its `CLAUDE.md`. Preserve existing user documents and customized workflow rules. If different instructions already govern those notes, reconcile the workflow instead of mixing incompatible schemas. Set the codebase/notes paths in `progress.md`; leave unknown facts explicitly unknown.
7. **Keep local configuration local.** In a Git codebase, use its local exclude file (`git rev-parse --git-path info/exclude`) for `CLAUDE.local.md`, local backup files if any, and only the four installed skill directories when using project-local installation. Preserve existing exclusions. Do not broadly ignore an existing `.claude/` directory, modify tracked skills, or hide tracked changes. If a requested local-only file is already tracked, explain that exclusions do not untrack it and preserve it pending a suitable choice. The sibling notes folder needs no exclusion from the codebase. Do not initialize Git in the notes folder unless requested.
8. **Verify the installation.** Confirm all four skills and supporting files exist; the binding resolves to the intended notes directory; all seven note files exist; installed references resolve; and existing work remains intact. Inspect the resulting changes. Note any partial installation or remaining access problem precisely.
9. **Activate and initialize.** Explain how to open the notes folder in Obsidian, start Claude in the codebase, and grant notes access. A fresh Claude session is the simplest way to ensure newly installed instructions and skills are loaded. If initialization is requested in the current session, read the installed `project-start/SKILL.md` explicitly and follow it; do not assume installation itself loaded the instructions. End with actual locations and the next command to run.

For repeated setup, inspect and merge rather than resetting documents or adding duplicate instruction sections. When installing a later version, compare installed files with the source and preserve local adaptations; version upgrades are deliberate merges, not automatic replacement.

## Resulting layout

With personal installation:

```text
~/.claude/
    CLAUDE.md
    skills/
        project-start/
        project-plan/
        project-resume/
        project-walkthrough/

workspace/
    my-project/
        CLAUDE.md             # Existing project instructions, if any
        CLAUDE.local.md       # Personal binding to ../my-project-notes
        ...                   # Application code
    my-project-notes/
        CLAUDE.md             # Detailed documentation workflow
        design.md
        requirements.md
        tasks.md
        decisions.md
        technical_architecture.md
        progress.md
```

The downloaded `project-workflow` repository can live elsewhere. Installed skills include their own templates and references; project notes stay separate from the reusable distribution.

## Start and resume work

From the codebase directory, launch Claude normally:

```bash
claude
```

Grant access to the sibling notes directory if it is not already available:

```text
/add-dir ../my-project-notes
```

Then initialize or adopt the project context:

```text
/project-start
```

You can supply a notes path explicitly when no binding exists:

```text
/project-start ../my-project-notes
```

An explicit relative path is resolved from Claude's working directory. A configured relative path is resolved from the codebase's `CLAUDE.local.md`. A conflicting saved binding must be reconciled before changing the persistent project association.

Write rough ideas or supplied context in `design.md`, then refine them with Claude:

```text
/project-plan Refine the design into requirements and tasks.
```

When ready, ask Claude to implement the selected task. Notes update automatically as work progresses; no checkpoint command is required.

For a fresh session, start Claude in the same codebase, ensure it can access the notes, and invoke:

```text
/project-resume
```

To understand the current implementation:

```text
/project-walkthrough Explain the request path and its failure behavior.
```

For an interactive understanding check:

```text
/project-walkthrough quiz
```

Open the notes directory as an Obsidian vault to edit and navigate the documents. Obsidian is optional; standard Markdown editors work too.

## How the documents stay current

| Document | Maintained information |
| --- | --- |
| `design.md` | Proposed and agreed design, constraints, alternatives, open questions |
| `requirements.md` | Desired outcomes, acceptance criteria, confirmation, verification evidence |
| `tasks.md` | Work items, dependencies, statuses, completion conditions, next actions |
| `decisions.md` | Consequential choices, rationale, tradeoffs, provenance, superseded decisions |
| `technical_architecture.md` | Actual implementation with concrete execution paths and source references |
| `progress.md` | Current state and chronological changes, discoveries, check results, blockers, and commit references |

Updates happen as meaningful events occur: a requirement changes, a task starts, a choice is adopted, behavior changes, a check runs, or a blocker appears. Before responding, the agent reconciles any remaining updates. It updates affected sections rather than rewriting every file after every tool call.

Tasks distinguish `todo`, `in_progress`, `implemented`, `verified`, and `done`, with `blocked` and `deferred` states. Non-code work uses appropriate completion evidence. Detailed semantics live in the [notes workflow](skills/project-start/assets/notes/CLAUDE.md).

This is an instruction-based workflow. It improves consistency but does not enforce updates mechanically. Evaluate it through actual usage: check whether notes match the working tree and whether a fresh session can recover the next task accurately.

## Claude Code loading and access

- Personal instructions belong in `~/.claude/CLAUDE.md`; project-local personal instructions belong in `CLAUDE.local.md` and load alongside the codebase's shared instructions.
- Skills can be installed personally in `~/.claude/skills/` or per project in `.claude/skills/`.
- Naming a sibling folder in Markdown does **not** grant access. Use `/add-dir` as needed and check access in a fresh session.
- Additional directories' `CLAUDE.md` files are not loaded automatically by default. The project binding and skills explicitly require reading the notes workflow.
- Use `/context` to inspect loaded memory files. After installing or changing configuration, start a fresh session and confirm the four skills are available. If a skill is unavailable, read its installed `SKILL.md` directly while diagnosing discovery; do not assume it ran.
- Personal instructions remain general; project-specific paths belong only in the project's local binding.

Official references: [Memory and CLAUDE.md](https://code.claude.com/docs/en/memory), [skills and installation locations](https://code.claude.com/docs/en/skills), and [Claude Code best practices](https://code.claude.com/docs/en/best-practices). Features can vary with installed version and managed settings.
