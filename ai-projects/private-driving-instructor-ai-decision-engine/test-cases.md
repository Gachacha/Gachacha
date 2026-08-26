# Decision Engine Test Cases

## Test 1 — Normal commute case
Verified data matches an approved commute rule → recommend approved commute pathway.

## Test 2 — Missing licence status
Required licence information is unknown → ask for or obtain verification before dependent decisions.

## Test 3 — Sensitive override
Normal confidence rule matches, but serious accident + severe fear is present → human escalation takes priority.

## Test 4 — Unverified licence
Customer states licence is valid but verification is pending → verify before dependent recommendation.

## Test 5 — Customer preference differs
System recommends commute pathway; customer requests a 2-hour assessment → preserve both and follow approved preference-handling process.

## Test 6 — No matching rule
Information is complete and verified, but no approved rule matches → human review.

## Test 7 — Conflicting information
Customer provides contradictory experience claims → preserve conflict and require clarification before dependent decisions.

## Test 8 — New situation outside authority
AI has a plausible solution but no approved rule covers the situation → do not invent policy; escalate.

## Test 9 — Multiple objectives
Customer wants both confidence recovery and immediate commuting → apply approved priority logic; if rules do not resolve the conflict, human review.

## Test 10 — Licence uncertainty before recommendation
Customer's licence is uncertain while an otherwise matching commute rule exists → verify licence first.
