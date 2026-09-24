# Day 20 — AI Workflow Guardrails

## Project 007 — AI Lead Processing Automation

### Core principle

AI operates under the authority of approved business rules. Guardrails control what the AI is permitted to do, while the state machine controls workflow position and allowed transitions.

## Guardrail architecture

### 1. Required-information guardrail
- Check: Required customer information is present and valid.
- Not allowed: Guess missing information or make unsupported package/terms decisions.
- Failure: Request missing information; escalate to HUMAN_REVIEW if unresolved.

### 2. Business-rule authority guardrail
- Check: Customer information is evaluated against approved business rules.
- Not allowed: Override, change, invent, or bypass approved business rules.
- Failure: Stop the automated decision and escalate to HUMAN_REVIEW.

### 3. Booking-authority guardrail
- Check: Required information is validated, the customer is qualified, and requested booking conditions are permitted.
- Not allowed: Book before required states and conditions are satisfied, or invent/override booking conditions.
- Failure: Preserve the process ID, identify the current state, and follow the approved transition such as NEEDS_INFORMATION or HUMAN_REVIEW.

### 4. External-failure guardrail
- Check: Use the unique process/booking ID to determine whether an external booking request produced a confirmed result.
- Not allowed: Treat an unverified result as a successful booking.
- Failure: Move to BOOKING_STATUS_UNKNOWN, reconcile the external system, then follow the approved recovery or escalation path.

### 5. Human-authority guardrail
- Check: Whether an approved business rule or recommendation covers the situation.
- Not allowed: Proceed with booking or invent a solution outside approved authority.
- Failure: Escalate to HUMAN_REVIEW.

## State and guardrail relationship

- Business rules determine the approved decision.
- Guardrails control AI authority and prohibited behaviour.
- The state machine controls workflow position and permitted transitions.
- External actions must be verified before a confirmed success state is recorded.

## Reliability principle

A timeout does not prove success or failure.

BOOKING_PENDING → BOOKING_STATUS_UNKNOWN → reconcile using Process ID → verify external result → determine approved next state.

Unknown is a valid state and must not be silently converted into failure or success.

## Day 20 test result

Recall: 10/10  
Build: 5/5  
Test: 9/10

The only test error was treating an unconfirmed booking as FAILED. Correct principle: an unconfirmed result remains unknown until reconciled.

## Portfolio statement

I designed guardrails for an AI lead-processing workflow that keep AI decisions and actions within approved business rules. The system validates required information, prevents unsupported decisions, controls booking authority, handles external timeouts through reconciliation, and escalates situations outside approved authority to human review.
