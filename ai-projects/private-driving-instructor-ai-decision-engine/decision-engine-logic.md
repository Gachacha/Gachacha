# Decision Engine Logic

```text
IF sensitive_case = YES
    → HUMAN ESCALATION
ELSE IF required_information_missing = YES
    → ASK QUESTIONS
ELSE IF required_information_unverified = YES
    → VERIFY
ELSE IF approved_rule_matches = YES
    → RECOMMEND APPROVED PATHWAY
ELSE
    → HUMAN REVIEW
```

## Authority boundary

The AI must not invent new business rules, select outcomes outside approved policy, or convert its own recommendation into a customer selection.

## Customer preference

Store customer preference separately from system recommendation. If the preference differs from the recommendation, follow the approved process for handling that difference.
