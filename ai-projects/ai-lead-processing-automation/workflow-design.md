# Workflow Design

## Normal path

```text
NEW
 ↓
EXTRACTED
 ↓
VALIDATION
 ↓
VERIFIED
 ↓
DECISION ENGINE
 ↓
QUALIFIED
 ↓
RECOMMENDATION_SENT
 ↓
CUSTOMER_DECISION
 ↓
BOOKED
```

## Exception paths

### Missing required information
`EXTRACTED → VERIFICATION_REQUIRED → obtain/verify → continue`

### Verification failure
Remain outside the verified path and follow the approved verification-failure process or route to human review.

### Sensitive case
`EXTRACTED/VERIFIED → HUMAN_REVIEW` when the sensitive-case rule has priority.

### Conflicting information
`EXTRACTED → HUMAN_REVIEW` or clarification process before dependent qualification.

### No matching approved rule
`VERIFIED → HUMAN_REVIEW`

### Customer rejects recommendation
Preserve the recommendation and customer preference separately; follow the approved alternative-request process.

## Duplicate-action protection

Before sending a recommendation or performing another non-repeatable action, check whether the action has already been completed. Record completion after successful execution.
