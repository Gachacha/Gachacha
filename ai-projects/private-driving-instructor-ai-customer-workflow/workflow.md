# Workflow Specification

## 1. Input
The customer's message.

## 2. Process
The AI:
1. Extracts relevant customer information.
2. Classifies the enquiry.
3. Identifies missing information.
4. Checks the available information against approved business rules.

### Core customer fields
- Licence status
- Driving experience
- Time away from driving
- Customer objective
- Requested training/package
- Location where relevant

## 3. Validate
The AI must distinguish between information stated by a customer and information that has been verified.

Example:
- Customer says: "I have paid."
- System status: Payment claimed, not verified.

The system must use the approved validation method before treating payment as confirmed.

## 4. Decide
The AI applies approved rules.

### Normal path
If the customer meets the approved eligibility requirements, continue with the approved package and next step.

### Missing information
Stop, ask, collect, then decide.

### Exception path
If the case falls outside the standard rules:
1. Check for an approved exception rule.
2. If one exists, follow it.
3. If none exists, escalate to a human.

### Sensitive path
Sensitive, high-risk, or judgment-based matters are escalated to a human.

## 5. Output
The system should produce structured information such as:

- Licence status
- Driving experience
- Time away from driving
- Customer objective
- Package match
- Eligibility status
- Missing information
- Recommended next step

Possible status values:
- Eligible
- Not eligible
- More information required
- Human review required

## 6. Action
Depending on the result, the system may:
- Answer an approved FAQ
- Ask a qualifying question
- Recommend an approved package
- Provide approved payment instructions
- Confirm the next step
- Initiate booking after required verification
- Escalate to a human

## 7. Human handoff
Human judgment is required for sensitive matters, unusual cases, undefined exceptions, conflicting information that cannot be resolved through approved questions, and decisions outside the approved rules.
