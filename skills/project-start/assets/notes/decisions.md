# Decisions

Record meaningful decisions in the table below. Use **agent**, **human**, or **both** in the Decided by column.

Use free-form notes for the context, source, reasoning, alternatives, tradeoffs, and code references that are useful. These are prompts for relevant detail, not required fields. Do not invent a rationale or alternatives that were never considered.

Use `both` only when the human and agent actually made the decision together; silence is not joint agreement. If the decision maker is unclear, say so rather than guessing. Identify the person when useful.

Make proposals and later changes clear in the notes. Preserve earlier decisions when they are replaced, explaining what changed. Add dates or IDs within the notes when they help navigation.

| Decision | Decided by | Notes |
| --- | --- | --- |

## Example — illustrative only

This fictional customer-import example demonstrates the format. It is not a project requirement, decision, implementation, or verification result. Keep examples separate from live entries; do not copy their IDs or results into project state.

| Decision | Decided by | Notes |
| --- | --- | --- |
| Reject a customer CSV if it is missing the `email` column. | both | The user confirmed that every imported customer must have an email. Rejecting the file before creating customers lets the user correct it and retry. Skipping invalid rows would make it harder to tell which customers were imported. The error should name the missing column. |
