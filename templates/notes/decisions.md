# Decisions

Use one subheading per decision and short labeled bullets rather than tables. Use **agent**, **human**, or **both** for who decided; say when it is unknown. Include rationale, alternatives, tradeoffs, and references only where useful.

## Decisions

### [Short decision title]

- **Decision:** [What was decided, in one sentence.]
- **Decided by:** [agent, human, both, or unknown.]
- **Rationale:** [Why this choice matters.]
- **Alternatives / tradeoffs:** [Relevant alternative and consequence; omit if unnecessary.]
- **References:** [Source or related note; omit if unnecessary.]

## Example (fictional)

### Reject CSVs with a missing email column

- **Decision:** Reject a customer CSV before creating customers if the `email` column is missing; name the missing column in the error.
- **Decided by:** both
- **Rationale:** The user confirmed every imported customer must have an email. Rejecting the file lets them correct it and retry.
- **Alternatives / tradeoffs:** Skipping invalid rows would make it harder to tell which customers were imported.
