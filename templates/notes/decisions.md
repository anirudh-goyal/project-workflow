# Decisions

Use **agent**, **human**, or **both** for who decided. Keep reasoning, alternatives, and tradeoffs in Notes where useful.

| Decision | Decided by | Notes |
| --- | --- | --- |

## Example (fictional)

| Decision | Decided by | Notes |
| --- | --- | --- |
| Reject a customer CSV if it is missing the `email` column. | both | The user confirmed that every imported customer must have an email. Rejecting the file before creating customers lets the user correct it and retry. Skipping invalid rows would make it harder to tell which customers were imported. The error should name the missing column. |
