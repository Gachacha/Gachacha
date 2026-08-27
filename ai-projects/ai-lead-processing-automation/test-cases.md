# Project 007 Test Cases

| Test | Input / condition | Expected result |
|---|---|---|
| 1 | New enquiry, licence missing | `NEW → EXTRACTED → VERIFICATION_REQUIRED` |
| 2 | Recommendation sent, no customer response | Remain at recommendation/customer-decision stage; do not mark booked |
| 3 | Verification fails | Do not enter `VERIFIED`; follow failure/review process |
| 4 | Workflow runs again after recommendation was already sent | Do not send duplicate recommendation |
| 5 | Verified customer has no matching approved rule | `VERIFIED → HUMAN_REVIEW` |
| 6 | Sensitive case plus normal package match | Sensitive rule takes priority → `HUMAN_REVIEW` |
| 7 | Customer requests an alternative to recommendation | Record preference separately and follow approved alternative process |
| 8 | Conflicting customer data | Require clarification/review before dependent decision |
| 9 | Situation outside AI authority | `HUMAN_REVIEW` |
| 10 | Unverified licence plus serious accident/severe fear | Sensitive-case priority → `HUMAN_REVIEW` |

## Result

All 10 test scenarios were evaluated during Day 16 training. Score: **9/10**. The single error involved incorrectly prioritising verification over a higher-priority sensitive-case escalation.
