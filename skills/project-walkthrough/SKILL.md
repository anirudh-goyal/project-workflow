---
name: project-walkthrough
description: Explain a project's current implementation and consequential decisions using source code and verification evidence, or rehearse understanding through questions. Use for a code walkthrough, demo preparation, or a requested knowledge check.
---

# Walk through the implementation

1. Follow [context resolution](../project-start/references/context.md). Read the relevant requirements, architecture, decisions, tasks, and progress evidence, then inspect the actual code.
2. Trace a concrete input through the relevant entry point, state changes, output, and failure behavior. Cite repository-relative files and precise symbols.
3. Explain consequential choices, their constraints and alternatives, and actual limitations. Attribute decisions accurately; do not invent a rationale or imply user review.
4. For a demo request, produce a short repeatable sequence using existing run instructions, expected observations, and known limitations. Use a real implemented path. Verify execution if requested or necessary and permitted; otherwise label the sequence unverified. Do not build a UI or modify the application unless asked.
5. For `quiz`, ask one question at a time about the actual implementation. Wait for the answer, assess it against the code, and explain gaps plainly. Focus on behavior and judgment rather than trivia.
6. Fix stale documentation discovered during the walkthrough according to the notes workflow. Record actual discoveries or checks, not speculative achievements. A walkthrough is not permission to refactor or fix code.

Keep the initial explanation concise and expand on request. The user should be able to locate and explain the actual implementation afterward.
