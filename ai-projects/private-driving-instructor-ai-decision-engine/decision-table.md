# Decision Table

| Priority | Conditions | Outcome |
|---|---|---|
| 1 | Sensitive case requiring judgment | Human escalation |
| 2 | Required information missing | Ask for missing information |
| 3 | Required information unverified | Verify information |
| 4 | Approved rule matches verified data | Recommend approved pathway |
| 5 | No approved rule matches | Human review |

## Examples

### Case A
Verified valid licence + experienced + long absence + confidence objective + no sensitive issue → confidence pathway.

### Case B
Licence unknown → verify before dependent decision.

### Case C
Verified valid licence + experienced + commute objective + all information verified + commute rule matches → commute pathway.

### Case D
Serious accident + severe fear → human escalation overrides normal package rule.

### Case E
Complete verified information but no approved rule matches → human review.
