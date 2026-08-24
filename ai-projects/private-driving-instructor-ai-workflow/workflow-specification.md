# Workflow Specification

## 1. Input
Customer message or enquiry.

## 2. Extract
Extract the approved qualification fields:
- Licence status
- Driving experience/period
- Time away from driving
- Customer objective
- Desired training duration

## 3. Qualify
Determine whether the required qualification information is present.

If information is missing, ask the approved qualifying questions.

## 4. Validate
Check extracted information against approved requirements and available verification methods.

Important distinction:
- Extraction = what the customer said.
- Validation = whether the information can be accepted for the decision.

## 5. Decide
Use approved business rules to select the correct path:

### Normal case
Customer meets approved requirements → continue with approved package process.

### Missing information
Required information is absent → ask approved qualifying questions.

### Exception / sensitive / undefined case
The situation requires judgment or is not covered by an approved rule → stop the normal automated path and escalate appropriately.

## 6. Action
For a qualified normal case:
- Recommend the approved package.
- Provide approved information and price.
- Proceed to the approved payment process.

## 7. Verify
Payment claims must be verified using the approved verification method.

Payment claimed ≠ payment confirmed.

## 8. Book
Only proceed to booking when the required booking conditions, including payment verification where applicable, are satisfied.

## 9. Output
Produce the relevant customer status, recommendation, next action, payment/booking status, and escalation status.

## 10. Human escalation
Escalate when the case is:
- Sensitive
- Conflicting
- Undefined
- Outside approved business rules
- Outside approved scope
- Dependent on human judgment

## System principle
**AI handles defined work. Humans handle judgment.**
