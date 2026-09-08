# Project notes workflow

These documents are the shared working context for the user and coding agent. Keep them current automatically while work happens, including incomplete or unsuccessful work. This file governs documentation for the bound codebase throughout the session, not only edits inside this folder.

## Read and recover

- Read this file at project start and in every fresh session before planning or implementation.
- Read progress.md's current state, active requirements/tasks, relevant design/decisions/architecture, then verify relevant claims against the codebase and working tree.
- Resolve code paths against the codebase recorded in progress.md. Check a moved or different checkout before assuming the notes apply.
- Treat source behavior, executed checks, and current user instructions as evidence. Surface material contradictions; never silently merge conflicting intent.
- Read older history on demand. Do not load the entire repository or repeat all past checks solely to recover context.

## Document ownership

| File | Maintained content |
| --- | --- |
| [[design]] | Problem, scope, proposed approach, supplied constraints, assumptions, alternatives, and open questions. Distinguish proposed and agreed sections. |
| [[requirements]] | Desired observable behavior, R- IDs, acceptance criteria, confirmation and verification status. |
| [[tasks]] | Executable work, T- IDs, linked requirements, dependencies, status, completion conditions, and evidence. |
| [[decisions]] | Short decision notes, who decided (agent, human, or both), and useful context. |
| [[technical_architecture]] | The system as implemented: existing behavior, our changes, execution paths, state ownership, failure handling, code/test references, and limitations. |
| [[progress]] | Current working state plus an append-only chronological record of meaningful work, discoveries, failed approaches, verification, and real commit references. |

Design describes intent; architecture describes reality. Requirements describe outcomes; tasks describe work. Link between them rather than repeating full explanations.

## Update as work happens

| Event | Required update |
| --- | --- |
| Requirement or constraint changes | Update requirements and affected design/tasks; preserve the reason and source of scope changes. |
| Task begins or changes state | Update tasks immediately and progress.md's current task/next action. |
| Consequential decision is proposed or adopted | Record a short note, making clear whether it is proposed or decided and who decided; update affected design. |
| A meaningful behavior change is implemented | Update the relevant architecture section and task state, even if unverified or broken. |
| A relevant check runs | Record command, working directory, result, and what it establishes. Link requirement/task evidence and update statuses accurately. |
| A blocker or useful failed approach is discovered | Record it when discovered, including the attempted approach, observation, and next action. |
| A commit is created under separate authorization | Record the actual hash and scope; distinguish changes left uncommitted. |
| Before a response or session handoff | Reconcile any pending notes updates for work already performed. Do not defer all maintenance to this point. |

- Update affected sections after each meaningful event or tightly related edit/check batch. Do not wait for a checkpoint command or session end.
- Do not log every file read or shell command. Group repeated checks of the same unchanged state; preserve failures and changed results that matter.
- Keep current-state sections concise. Append dated progress entries; never rewrite historical evidence to appear more successful.
- Record partial state honestly. Do not manufacture certainty, requirements, decisions, commit hashes, test results, or user agreement.
- Preserve user edits and customized structure. Resolve contradictions with the user when evidence cannot establish intent.
- Note updates are part of task completion. Do not mark work done while affected documents describe an obsolete implementation.

## Requirements and task status

Requirements use stable R-001-style IDs. Record confirmation (`proposed` or `confirmed`) separately from delivery (`not_started`, `implemented`, or `verified`). Superseded or withdrawn requirements retain an explanation and link to replacements. Verification requires evidence for the actual acceptance criteria; implementation alone is insufficient.

Tasks use stable T-001-style IDs and these statuses:

| Status | Meaning |
| --- | --- |
| todo | Work has not started. |
| in_progress | Work is underway; identify the current next action. |
| implemented | The deliverable exists; required verification remains. |
| verified | Relevant completion checks passed; final documentation reconciliation may remain. |
| done | Completion evidence is recorded and affected documentation is current. |
| blocked | Record the blocker, prior state, and action needed to unblock. |
| deferred | Record why it is deferred and who made that scope decision. |

A non-code task can move directly to done when its appropriate completion condition is met; do not invent executable checks. Failed checks or changed relevant code require an accurate status adjustment and preserved history. Do not label user review as complete unless it happened.

## Decisions

Record meaningful decisions as short, free-form notes. State the decision and who decided it: **agent**, **human**, or **both**. Include context, source, reasoning, alternatives, tradeoffs, and references where useful; do not require separate fields for each. Use `both` only for an actual joint decision, and say when attribution is unknown. Make proposals and replaced decisions clear without imposing a fixed status schema. Dates and IDs are optional navigation aids. Routine decisions within authorized scope do not require a separate approval; material choices outside agreed scope do.

## References and evidence

- Use Obsidian wikilinks such as [[design]] between notes. Use folder-qualified targets when names collide in a larger vault.
- For source code, use relative Markdown file links from the note to the real file plus its precise function/class name. Prefer paths and symbols over brittle line numbers alone. Repair affected links when files move.
- Separate supplied facts, inspected behavior, assumptions, proposals, and executed evidence.
- A check record includes an absolute date/time with time zone, actual working directory and command, result, and relevant code state (HEAD plus dirty-state description when applicable). Refer to it elsewhere instead of duplicating output.
- Record short relevant output or counts, not raw noisy logs. Do not copy credentials, secrets, or unrelated personal material into notes.
- Creating or updating notes does not authorize commits, pushes, or changes to unrelated configuration. Record uncommitted work as uncommitted.
