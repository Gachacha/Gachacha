# Data Structuring Test Cases

## Test 1 — Ambiguous experience
Input: "I've been driving for many years."
Expected: `driving_experience: many years`; no invented number.
Result: PASS

## Test 2 — Vague time away
Input: "I stopped recently."
Expected: `time_away_from_driving: recently — exact duration unknown`.
Result: PASS

## Test 3 — Conflicting licence information
Input: "My licence is valid. Actually, I think it expired two months ago."
Expected: `licence_status: conflicting/uncertain — requires verification`.
Result: PASS

## Test 4 — AI inference separated from customer data
Input: "I need to drive from Karen to Westlands every morning for work."
Expected: Current location, destination, and objective are extracted; package recommendation remains an AI/workflow output.
Result: PASS

## Test 5 — Verification
Input: "My licence is valid."
Expected: Record customer-stated status, then use approved verification before decisions requiring confirmed validity.
Result: PASS

## Test 6 — Missing required field
Input: "I'm licensed, I've driven for years, and I want to become confident again."
Expected: `time_away_from_driving: unknown`; ask approved question.
Result: PASS

## Test 7 — Sensitive situation
Input: Customer reports a serious accident and asks for a guarantee that training will cure anxiety.
Expected: Extract relevant information, avoid unsupported guarantee, and route judgment appropriately.
Result: PASS

## Test 8 — Full uncertainty preservation
Input: "I've been driving for about 8 years, but I haven't driven since sometime in 2023. I think my licence is still valid. I want to drive to work in Westlands."
Expected: Preserve "about," preserve uncertain time range, mark licence uncertain, and extract Westlands as destination.
Result: PASS

## Summary
**7/8 stress-test questions answered correctly in the learning session.**
