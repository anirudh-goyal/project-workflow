# Design

## Problem and intended outcome

Not yet captured.

## Supplied constraints and scope

## Proposed approach

## Agreed approach

## Alternatives and tradeoffs

## Assumptions and open questions

## Related documents

[[requirements]] · [[tasks]] · [[decisions]] · [[technical_architecture]]

## Example — illustrative only

This fictional customer-import example demonstrates the format. It is not a project requirement, decision, implementation, or verification result. Keep examples separate from live entries; do not copy their IDs or results into project state.

**Problem:** A customer CSV without the required `email` column should produce an actionable error before any customers are created.

**Agreed approach:** Validate headers before processing rows. Have the upload endpoint translate a missing-column error into HTTP 400 with the column name.

**Alternative considered:** Skip invalid rows. Rejected because the user wants to fix and retry the complete file rather than investigate a partial import.

**Open question:** Whether header matching should be case-insensitive.

This describes the intended behavior. Implementation progress belongs in [[tasks]] and [[technical_architecture]].
