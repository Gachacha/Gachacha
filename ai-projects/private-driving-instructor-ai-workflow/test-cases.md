# Workflow Stress Tests

## Test 1 — Normal qualified customer
Expected path: Extract → Qualify → Validate → Approved package → Payment.

**Result: PASS**

## Test 2 — Missing information
Expected path: Identify missing information → Ask approved qualifying questions → Continue qualification.

**Result: PASS**

## Test 3 — Exception request
Customer lacks a required licence but requests an exception.
Expected path: Apply approved rule → stop normal booking path → escalate for human judgment if appropriate.

**Result: PASS**

## Test 4 — Unverified payment
Customer claims payment has been made but there is no verification.
Expected path: Record claim as unverified → use approved payment verification → book only after confirmation.

**Result: PASS**

## Test 5 — Conflicting information
Customer gives contradictory licence information.
Expected path: Detect conflict → clarify or escalate → do not guess.

**Result: PASS**

## Test 6 — Sensitive situation
Customer reports a serious accident and asks for a guarantee that training will remove fear.
Expected path: Avoid unsupported guarantee → human judgment.

**Result: PASS**

## Test 7 — Out-of-scope request
Customer asks the driving-training workflow to guarantee insurance claim payment.
Expected path: Recognize scope boundary → approved response or appropriate escalation.

**Result: PASS**

## Summary
**7/7 workflow stress tests passed.**
