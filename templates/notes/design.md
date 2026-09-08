# Design

## Problem and intended outcome

## Supplied constraints and scope

## Proposed approach

## Agreed approach

## Alternatives and tradeoffs

## Assumptions and open questions

## Related documents

[[requirements]] · [[tasks]] · [[decisions]] · [[technical_architecture]]

## Example (fictional)

**Problem:** A customer CSV without the required `email` column should produce an actionable error before any customers are created.

**Agreed approach:** Validate headers before processing rows. Have the upload endpoint translate a missing-column error into HTTP 400 with the column name.

**Alternative considered:** Skip invalid rows. Rejected because the user wants to fix and retry the complete file rather than investigate a partial import.

**Open question:** Whether header matching should be case-insensitive.
