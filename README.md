# Project Workflow

My preferred way of working on software projects with coding agents: preserve context across sessions, keep decisions explicit, and stay informed as the implementation evolves.

Claude follows my working preferences and maintains a shared set of Markdown notes while we work. A fresh session reads those notes and checks the actual code before continuing. Obsidian provides a convenient way to read and edit the documents, but any Markdown editor works.

The setup uses normal Claude Code features. No scripts, launcher, or plugins are required.

## What is in this repository

```text
project-workflow/
    CLAUDE.md
    skills/
        project-start/SKILL.md
        project-resume/SKILL.md
    templates/
        CLAUDE.local.md
        notes/
            CLAUDE.md
            design.md
            requirements.md
            tasks.md
            decisions.md
            technical_architecture.md
            progress.md
```

- **[CLAUDE.md](CLAUDE.md):** general preferences for communication, collaboration, code, and keeping notes current.
- **[Skills](skills/):** two commands for beginning a project and continuing it in a new session.
- **[CLAUDE.local.md template](templates/CLAUDE.local.md):** tells Claude where a particular project's notes live.
- **[Note templates](templates/notes/):** copied into your project's notes folder during setup. The [notes CLAUDE.md](templates/notes/CLAUDE.md) explains how to maintain them. Each of the six documents includes an illustrative example.

Once setup is complete, the installed skills work with your project notes. They do not need the downloaded repository or their own template copies.

## Set up with Claude

Clone this repository:

```bash
git clone https://github.com/anirudh-goyal/project-workflow.git
```

Give Claude access to the downloaded repository and your target directories, using `/add-dir` if needed. Replace the example paths below with real absolute paths.

### Existing codebase

Start Claude in your codebase and send:

```text
Read /absolute/path/project-workflow/README.md and set up this workflow.

Codebase: /absolute/path/my-project
Notes: /absolute/path/my-project-notes

Install preferences and skills globally if possible, otherwise locally
in this project. Preserve existing instructions, notes, and code changes.
Initialize the notes, but do not change application code or commit/push.
```

### New codebase

Start Claude in the directory where you want to create the project and send:

```text
Read /absolute/path/project-workflow/README.md and set up this workflow.

New codebase: /absolute/path/my-project
Notes: /absolute/path/my-project-notes

Create the codebase directory and initialize a local Git repository.
Install preferences and skills globally if possible, otherwise locally.
Prepare the notes, but do not scaffold an application or commit/push yet.

My initial idea is: [describe the project]
```

If you do not want Git yet, omit the instruction to initialize it. If the directory already contains a project, adopt it rather than replacing it.

## Setup instructions for Claude

Use the user's supplied paths. Preserve existing files and customizations, inspect Git status, and merge compatible instructions instead of overwriting them. Ask only about missing information, meaningful conflicts, or required access.

1. **Install preferences and skills.** Merge this repository's `CLAUDE.md` into `~/.claude/CLAUDE.md` and copy the two skill folders into `~/.claude/skills/`. For local installation, put preferences in the codebase's `CLAUDE.local.md` and skills in its `.claude/skills/`. Preserve the codebase's shared `CLAUDE.md`.
2. **Prepare the notes.** Copy missing files from `templates/notes/` into the chosen notes folder. Keep existing notes and their rules. Record the actual codebase and notes paths in `progress.md`; leave unknown details unknown.
3. **Tell Claude where the notes are.** Add the section from `templates/CLAUDE.local.md` to the codebase's `CLAUDE.local.md`, replacing `../notes` with the correct path. Clarify before changing a different existing notes location.
4. **Check the result.** Verify both skills, all seven note files, and the notes path. Keep newly installed personal files out of commits using Git's local exclude file; preserve existing exclusions and tracked files. Do not commit or push as part of setup.
5. **Begin.** Tell the user the installed locations and next steps below. If asked to initialize notes in the current session, explicitly read and follow the installed start skill. Setup alone does not authorize application implementation.

Repeated setup should reuse existing files without duplicating instructions or resetting notes. Create directories and initialize Git only as requested. Keep project notes outside this reusable workflow repository.

## Daily use

Open the notes folder as an Obsidian vault. Launch Claude normally from the codebase:

```bash
claude
```

Ensure Claude can access the sibling notes folder:

```text
/add-dir ../my-project-notes
```

**First session:** run `/project-start`. Claude reads your initial notes, inspects the relevant code, and helps establish the project direction. You can supply the notes path directly: `/project-start ../my-project-notes`.

**During work:** talk normally. Ask to refine the design, break it into requirements and tasks, implement a task, or explain the code. Claude updates the notes as meaningful changes happen; no separate planning or checkpoint command is needed.

**Fresh session:** run `/project-resume`. Claude reads the notes, checks the actual code and working tree, and identifies what to do next. Ensure notes access is available in the new session too.

## The project notes

| File | What it records |
| --- | --- |
| `design.md` | What we propose to build and how, including open questions |
| `requirements.md` | What the system must do and how we know it works |
| `tasks.md` | The work needed to meet those requirements, with statuses and next actions |
| `decisions.md` | A table of decisions, who decided (agent, human, or both), and free-form notes |
| `technical_architecture.md` | How the implemented system works, with references to real code |
| `progress.md` | Current state and dated bullet entries covering changes, checks, blockers, and commits |

The notes folder's `CLAUDE.md` contains the update rules. Claude updates affected documents when requirements, decisions, implementation, task status, or verification change. It records failures and partial progress as well as successes.

The examples are fictional and separate from real project content. The workflow guides agent behavior; it does not mechanically guarantee that notes are updated. A useful check is whether a fresh session can accurately recover the current task from the notes and code.

## A few setup details

- `../notes` means a sibling folder; `/notes` means a folder at the filesystem root.
- A notes path in `CLAUDE.local.md` is relative to that file. A path passed to a skill is relative to Claude's working directory.
- A path written in Markdown does not grant access. Use `/add-dir` when needed.
- Additional directories' `CLAUDE.md` files are not automatically loaded by default. The codebase's local instructions and both skills explicitly tell Claude to read the notes instructions.
- After installing preferences and skills, start a fresh session. Use `/context` to check loaded instructions and confirm the two skills are available.
- If upgrading from the earlier four-skill version, remove the old `project-plan` and `project-walkthrough` installations only after checking for your custom changes. Replace the start/resume instructions with the current versions; retain your existing project notes. This repository update does not change global installations automatically.

Official references: [Claude Code memory](https://code.claude.com/docs/en/memory) and [skills](https://code.claude.com/docs/en/skills).
