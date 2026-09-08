# Project Workflow

My preferred way of working with coding agents: keep context across sessions, make decisions explicit, and stay informed as the code changes.

Claude follows my working preferences and maintains shared Markdown notes during development. A new session reads the notes and checks the code before continuing. The notes work in Obsidian or any Markdown editor.

## Structure

```text
CLAUDE.md                      General working preferences
skills/
    project-start/SKILL.md      Begin project work
    project-resume/SKILL.md     Continue in a fresh session
templates/
    CLAUDE.local.md             Tell Claude where the notes live
    notes/
        CLAUDE.md              How to maintain the notes
        design.md
        requirements.md
        tasks.md
        decisions.md
        technical_architecture.md
        progress.md
```

## Set up with Claude

Clone this repository:

```bash
git clone https://github.com/anirudh-goyal/project-workflow.git
```

Give Claude access to the downloaded repository and target directories using `/add-dir` as needed. Then use one of these prompts with your actual paths.

**Existing codebase** — start Claude in the codebase:

```text
Read /absolute/path/project-workflow/README.md and set up this workflow.

Codebase: /absolute/path/my-project
Notes: /absolute/path/my-project-notes

Install globally if possible, otherwise locally in this project.
Preserve existing work. Set up the notes without changing application
code or committing/pushing.
```

**New codebase** — start Claude in the parent directory:

```text
Read /absolute/path/project-workflow/README.md and set up this workflow.

New codebase: /absolute/path/my-project
Notes: /absolute/path/my-project-notes

Create the directory and initialize Git. Install globally if possible,
otherwise locally. Prepare the notes without scaffolding an application
or committing/pushing.

My initial idea is: [describe the project]
```

## Setup instructions for Claude

Use the supplied paths. Inspect existing instructions and Git status, preserve customizations, and merge additions without duplicating earlier setup. Ask about missing information, conflicting instructions, or required access.

1. **Install preferences and skills.** Merge [CLAUDE.md](CLAUDE.md) into `~/.claude/CLAUDE.md`; copy the two [skill folders](skills/) into `~/.claude/skills/`. For local installation, use the codebase's `CLAUDE.local.md` for preferences and `.claude/skills/` for skills. Preserve its shared `CLAUDE.md`.
2. **Create the notes.** Copy missing files from [templates/notes](templates/notes/) into the chosen notes folder. Keep existing notes and record the actual codebase and notes paths in `progress.md`.
3. **Record the notes location.** Add [templates/CLAUDE.local.md](templates/CLAUDE.local.md) to the codebase's `CLAUDE.local.md`, using the correct notes path. Clarify before changing an existing location.
4. **Check and finish.** Verify both skills, the seven note files, and the notes path. Exclude newly installed local-only files using Git's local exclude file, preserving tracked files and existing exclusions. Report the locations and how to begin below.

Keep project notes outside this downloaded repository. Create directories and initialize Git as requested; setup alone does not authorize application changes or commits. To initialize notes in the current session, read and follow the installed start skill explicitly.

## Working on a project

Open the notes folder as an Obsidian vault if desired. Start a fresh Claude session in the codebase:

```bash
claude
```

Grant access to the notes folder when needed:

```text
/add-dir ../my-project-notes
```

- **Begin:** `/project-start` reads initial notes and helps establish the next steps.
- **Work:** talk normally to refine the design, create tasks, implement changes, or explain code. Notes update automatically throughout.
- **Continue in a fresh session:** `/project-resume` reads the notes and checks the code and working tree.

Both skills use the notes path in `CLAUDE.local.md`. You can also supply a path directly, such as `/project-start ../my-project-notes`.

## The notes

| File | Purpose |
| --- | --- |
| `design.md` | What we propose to build and how |
| `requirements.md` | What the system must do and its acceptance criteria |
| `tasks.md` | Work items, statuses, dependencies, and next actions |
| `decisions.md` | Decision, who decided (agent, human, or both), and free-form notes |
| `technical_architecture.md` | How the implementation works, with code references |
| `progress.md` | Current state and dated progress bullets, including checks and commits |

Each document includes a fictional example. The [notes instructions](templates/notes/CLAUDE.md) define frequent updates as requirements, decisions, implementation, and results change.

## Access and loading

A path in `CLAUDE.local.md` is relative to that file; a path passed to a skill is relative to Claude's working directory. `../notes` is a sibling folder, while `/notes` is at the filesystem root.

Writing a path does not grant access: use `/add-dir` as needed. Additional folders' instructions are not automatically loaded by default, so the skills and local instructions explicitly tell Claude to read the notes' `CLAUDE.md`. After installation, start a fresh session and use `/context` to check loaded instructions.

Official documentation: [Claude Code memory](https://code.claude.com/docs/en/memory) and [skills](https://code.claude.com/docs/en/skills).
