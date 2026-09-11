# Keeping project notes

Maintain these documents throughout project work, including failures and partial progress. Update affected sections when something changes; do not wait for reminders or session end.

## What goes where

| File | Purpose |
| --- | --- |
| [[design]] | Proposed and agreed approach, constraints, and open questions |
| [[requirements]] | Desired behavior and acceptance criteria |
| [[tasks]] | Work items, dependencies, statuses, and completion evidence |
| [[decisions]] | What was decided, who decided, and useful context |
| [[technical_architecture]] | How our implementation and relevant surrounding systems work, with code references and run/test instructions |
| [[progress]] | Current state and dated bullet entries recording work and results |

Keep proposed design separate from implemented architecture. Link between notes rather than repeating explanations. Examples in the templates are fictional; keep them separate from live project content.

## When to update

- **Requirements or design change:** update the affected documents and tasks, including the reason for the change.
- **A task starts or changes state:** update its status and the current task in progress.
- **A decision is made:** add a decision note and update affected design sections.
- **Behavior is implemented:** update architecture and task status, even if unfinished or unverified.
- **A check runs or a blocker appears:** record the result, limitations, and next action in progress. Update affected task/requirement statuses.
- **A commit is created:** record its actual hash and scope. Otherwise describe changes as uncommitted.
- **Before responding:** reconcile any remaining updates for work already performed.

Record meaningful events, not every tool call. Append dated progress bullets; preserve earlier results and decisions. Keep current-state sections concise. Respect user edits, and ask about contradictions that the code or conversation cannot resolve.

## Statuses

Requirements have stable R- IDs, confirmation (`proposed` or `confirmed`), and delivery status (`not_started`, `implemented`, or `verified`). Verification needs evidence for the acceptance criteria. Retain a short explanation when requirements change or are withdrawn.

Tasks have stable T- IDs and these statuses:

| Status | Meaning |
| --- | --- |
| todo | Not started |
| in_progress | Work underway |
| implemented | Deliverable exists; verification remains |
| verified | Checks passed; documentation may remain |
| done | Completion evidence recorded and notes current |
| blocked | Include the blocker and next action |
| deferred | Include the reason and who decided |

Non-code tasks can go directly to done when their completion condition is met. Adjust statuses when failures or code changes invalidate earlier evidence.

## Writing notes

Apply this style throughout every notes document, including design, requirements, tasks, decisions, architecture, and progress.

- Write concisely for scanning in Obsidian. Lead with the current result or decision; keep paragraphs short and use bullets to separate distinct points. Aim for one idea and one or two short sentences per bullet. Split a long explanation into labeled bullets rather than moving a wall of text out of a table.
- Summarize the final choice and the reasoning needed to understand it. Omit conversational play-by-play, repeated explanations, and abandoned implementation details unless they explain a material tradeoff or constraint. Preserve meaningful changes of direction and their source in a short bullet.
- Keep detailed implementation explanations in [[technical_architecture]] and verification records in [[progress]]; link to them rather than duplicating them. Preserve evidence, uncertainty, and important limitations when shortening text.
- Requirements and tasks use one subheading per entry (stable ID plus short description) and labeled bullets for their fields, as shown in the templates. Keep these entries out of tables so long text wraps within Obsidian's reading pane. Preserve all fields, including confirmation, statuses, dependencies, and evidence.
- Decisions use one short subheading per entry and labeled bullets for **Decision**, **Decided by**, and useful rationale, alternatives, tradeoffs, or references. Do not use tables or a catch-all Notes paragraph. Decided by is **agent**, **human**, or **both**; say when it is unknown. Make proposals and replaced decisions clear. Do not infer joint agreement from silence.
- Use Obsidian wikilinks between notes and relative Markdown links to real code files, with function/class names. Use folder-qualified note links when names collide.
- For verification, record the actual command, working directory, result, date/time with time zone, and relevant code state. Summarize useful output rather than copying full logs or secrets.
- Never invent requirements, agreement, test results, or commit hashes. Mark assumptions and unverified behavior explicitly.
