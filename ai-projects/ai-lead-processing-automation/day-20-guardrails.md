# Day 20 — AI Workflow Guardrails

## Project 007 — AI Lead Processing Automation

### Core principle

The AI may act autonomously only when the current state, approved business rules, required evidence, and guardrails all permit the action.

## State Rules vs Guardrails

- **State rules** control when the workflow may move to another state.
- **Guardrails** control what the AI is allowed or prohibited from doing.
- **Business rules** determine the approved business decision.
- **Human authority** remains responsible for exceptions and changes to approved rules.

## Five Guardrails

### 1. Required Information Guardrail

**Check:** Confirm all required customer information is present and valid.

**Not allowed:** Guess missing information or make an unsupported package or terms decision.

**If it fails:** Request missing information and move to `NEEDS_INFORMATION`; escalate to `HUMAN_REVIEW` when the information cannot be resolved.

### 2. Business-Rule Authority Guardrail

**Check:** Check the customer's information against the approved business rules.

**Not allowed:** Override, change, invent, or bypass approved business rules.

**If it fails:** Stop the automated decision and escalate to `HUMAN_REVIEW`.

### 3. Booking Authority Guardrail

**Check:** Confirm required information is provided and validated, the customer is qualified, and the requested package/booking conditions are permitted by approved rules.

**Not allowed:** Book when required conditions or states have not been satisfied, or invent/override booking conditions.

**If it fails:** Keep the existing process ID, record the failure, identify the current state, and follow the approved transition such as `NEEDS_INFORMATION` or `HUMAN_REVIEW`. Do not restart the workflow unnecessarily.

### 4. External Failure and Timeout Guardrail

**Check:** Use the unique process/booking ID to determine whether the external booking request produced a confirmed result.

**Not allowed:** Treat an unverified result as a successful booking.

**If it fails:** Move to `BOOKING_STATUS_UNKNOWN`, reconcile the external system using the ID, then follow the approved recovery or human-escalation path.

Correct recovery pattern:

`TIMEOUT → BOOKING_STATUS_UNKNOWN → RECONCILE → BOOKED / RECOVERY_PENDING / HUMAN_REVIEW`

### 5. Human Authority Guardrail

**Check:** Determine whether an approved business rule or recommendation covers the situation.

**Not allowed:** Proceed to booking, invent a solution, or create an exception when no approved rule authorizes it.

**If it fails:** Stop and escalate to `HUMAN_REVIEW`.

## Controlled AI Workflow

`AI → STRUCTURED FACTS → BUSINESS RULES → GUARDRAILS → STATE TRANSITION → APPROVED ACTION → VERIFY RESULT → UPDATE STATE`

## Key Reliability Principles

1. AI intelligence does not equal AI authority.
2. Customer-provided information is not automatically verified information.
3. Qualification does not automatically mean booking.
4. An attempted action is not a confirmed state.
5. A timeout is not proof of success or failure.
6. A process ID identifies and tracks the workflow; it does not itself handle the failure.
7. The workflow should resume from the correct state rather than blindly restart.
8. AI may recommend changes to business rules, but authorized humans must approve those changes.
9. When approved rules cannot resolve a case, the AI must stop and escalate.

## Day 20 Assessment

- Learn: Complete
- Recall: 10/10
- Build: 5/5
- Test: 9/10
- Deploy: Complete
- Document: Pending
- Demonstrate: Pending
- Close: Pending

## Portfolio Statement

I designed guardrails for an AI lead-processing workflow that restrict what the AI can decide and do. The guardrails require validated information, enforce approved business rules, prevent unauthorized booking actions, control failure and timeout handling, and escalate exceptions to human review. This creates controlled autonomy rather than unrestricted AI decision-making.
