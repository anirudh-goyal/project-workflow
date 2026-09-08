# Decisions

Keep short notes about meaningful decisions. For each entry, state what was decided and **Decided by: agent, human, or both**.

Use free-form notes for the context, source, reasoning, alternatives, tradeoffs, and code references that are useful. These are prompts for relevant detail, not required fields. Do not invent a rationale or alternatives that were never considered.

Use `both` only when the human and agent actually made the decision together; silence is not joint agreement. If the decision maker is unclear, say so rather than guessing. Identify the person when useful.

Make proposals and later changes clear in the notes. Preserve earlier decisions when they are replaced, explaining what changed. Add dates or IDs when they help navigation; no fixed entry schema is required.

## Example — illustrative only

This fictional customer-import example demonstrates the format. It is not a project requirement, decision, implementation, or verification result. Keep examples separate from live entries; do not copy their IDs or results into project state.

**Decision:** Reject a customer CSV if it is missing the `email` column.

**Decided by:** both

**Notes:** The user confirmed that every imported customer must have an email. We chose to reject the file before creating any customers so the user can correct it and retry. Skipping invalid rows would make it harder to tell which customers were imported. The error should name the missing column.
