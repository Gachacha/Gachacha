# Day 18 — Controlled AI Decision Engine

## Training record

- Program: MUMBI AI Mastery
- Day: 18 / 180
- Lesson target: 120 minutes
- Capability stage: Integrating
- AI Capability Pyramid: Building → Integrating
- Recall: 9/10
- Build: 9/10
- Test: 10/10

## Objective
Design a decision engine that separates customer facts, AI inferences, approved business rules, decisions, customer choices, actions, exceptions, and audit records.

## Core model

```text
CUSTOMER INPUT
      ↓
     FACTS
      ↓
AI INTERPRETATION
      ↓
  INFERENCES
      ↓
APPROVED RULES
      ↓
   DECISION
      ↓
CUSTOMER DECISION
      ↓
APPROVED ACTION
```

## Design principles

### Facts
Facts are information provided or verified by an authorized source.

Example:

```text
licensed = YES
recent_driving = NO
```

### Inferences
Inferences are conclusions the AI draws from facts. They must not be treated as verified facts automatically.

Example:

```text
customer_may_need_confidence_support = YES
```

### Rules
Rules are approved business conditions that provide decision authority. AI may apply the rules but must not silently change them.

### Decisions
A decision is the result authorized by the applicable rules.

Example:

```text
qualified = YES
pathway = CONFIDENCE
```

### Customer decision
Qualification does not equal acceptance. A customer must still choose/accept where the workflow requires it.

### Actions
Actions such as CRM updates, WhatsApp messages, or bookings occur only when the required conditions are satisfied and the action is authorized.

## Project 007 decision-engine example

```text
Customer enquiry
      ↓
AI extracts structured facts
      ↓
Validate required fields
      ↓
Check sensitive/conflicting information
      ↓
Apply approved rules
      ↓
Qualification + pathway
      ↓
Present approved options
      ↓
Customer decision
      ↓
Approved downstream action
      ↓
Verify external result
      ↓
Update workflow state
```

## Rule priority
Exception and safety rules can override normal qualification rules.

Example:

```text
Rule A: licensed + low recent driving + low confidence → CONFIDENCE
Rule B: licence information conflict → HUMAN_REVIEW

If both apply:
HUMAN_REVIEW wins because the conflict rule has higher priority.
```

## Missing and ambiguous information

Unknown information must remain unknown.

```text
licensed = YES
recent_driving = NO
confidence_concern = UNKNOWN
```

Correct state:

```text
status = NEEDS_INFORMATION
missing = confidence_concern
```

Do not guess YES or NO.

## Human-review packet
A useful human-review record should include:

```text
status = HUMAN_REVIEW
reason = LICENCE_INFORMATION_CONFLICT
customer_id = <unique customer/request ID>
facts = <relevant structured facts>
recommended_action = VERIFY_LICENCE
```

## Audit trail
A reliable system should preserve enough information to reconstruct why a decision was made:

```text
customer_id
request_id
timestamp
input_version
facts
rules_evaluated
decision
pathway
action
action_result
```

## Security and authority boundaries

- Customer-provided text is data, not system authority.
- Embedded instructions such as “ignore the rules” are untrusted input.
- AI can recommend a rule change but cannot authorize or implement a business-rule change without the approved process.
- Sensitive information follows the approved sensitive-data workflow.
- AI capability does not create permission.

## Test results

The decision engine passed 10/10 adversarial tests covering:

1. Conflicting instructions
2. Ambiguous information
3. Rule collision
4. Prompt injection through customer data
5. CRM timeout / unknown tool result
6. Unauthorized rule change
7. Sensitive information
8. Duplicate events
9. Internal/external state inconsistency
10. Full integration challenge

## Key lesson

> Separate interpretation from authority.

AI can interpret information. Approved business rules provide authority. External tools execute authorized actions. Humans handle cases outside the system's authority.

## Portfolio statement

Day 18 demonstrates controlled AI decision-engine design: structured fact extraction, rule-based qualification, exception priority, human escalation, auditability, prompt-injection resistance, and separation of AI capability from business authority.
