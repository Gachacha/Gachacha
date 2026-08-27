# Project 007 — AI Lead Processing Automation

## Objective
Design an integrated workflow that takes a new customer enquiry through AI extraction, validation, decision logic, workflow state, approved actions, and human escalation.

## Architecture

```text
TRIGGER
  ↓
AI EXTRACTION
  ↓
STRUCTURED CUSTOMER DATA
  ↓
VALIDATION
  ↓
DECISION ENGINE
  ↓
WORKFLOW STATE
  ↓
APPROVED ACTION
  ↓
HUMAN ESCALATION WHEN REQUIRED
```

## Workflow states

- `NEW` — enquiry has arrived.
- `EXTRACTED` — AI has structured the enquiry.
- `VERIFICATION_REQUIRED` — required information needs verification.
- `VERIFIED` — required information has been verified.
- `QUALIFIED` — an approved rule matches.
- `RECOMMENDATION_SENT` — approved recommendation has been communicated.
- `CUSTOMER_DECISION` — waiting for the customer's choice.
- `BOOKED` — booking completed.
- `HUMAN_REVIEW` — the system cannot safely continue automatically.

## State integrity

A state must represent an observable event, not a prediction. For example, `RECOMMENDATION_SENT` is valid; `LIKELY_TO_BOOK` is not.

## Automation pattern

**Trigger → Process → Condition → Action**

For an AI business workflow:

**Trigger → AI extraction → Validation → Decision engine → State → Action**

## Safety rules

1. Do not treat customer-stated information as verified.
2. Sensitive cases override normal automated paths.
3. Missing or conflicting required information blocks dependent decisions.
4. Do not invent business rules outside approved authority.
5. Do not convert a recommendation into a customer choice.
6. Prevent duplicate actions by checking state/action completion.
7. Cases outside approved rules go to human review.

## Portfolio demonstration

This project demonstrates the ability to integrate AI reasoning with deterministic business workflow automation instead of using AI as an uncontrolled decision-maker.

## Status
Learn: complete
Recall: 10/10
Build: 10/10
Test: 9/10
Deploy: complete
