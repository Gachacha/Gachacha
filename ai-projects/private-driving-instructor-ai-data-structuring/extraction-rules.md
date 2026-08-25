# Extraction Rules

## Rule 1 — Extract, do not invent
Record only information supported by the customer's message.

## Rule 2 — Preserve precision
If the customer says "about 7 years," record "about 7 years," not "7 years exactly."

## Rule 3 — Preserve missing information
If a required field is not provided, record it as unknown / not provided. Do not guess.

## Rule 4 — Preserve uncertainty
If the customer says "I think my licence is valid," record the uncertainty and mark verification as required.

## Rule 5 — Preserve contradictions
If the customer gives conflicting statements, record the conflict and require clarification or verification.

## Rule 6 — Separate customer data from AI conclusions
A customer asking for a recommendation does not mean a package has been selected.

Example:
- `package_selected: none`
- `package_recommendation: pending`

## Rule 7 — Separate extraction from qualification
Extracted data describes what the customer said. Qualification determines whether the information meets approved business rules.

## Rule 8 — Separate extraction from verification
A structured field may still be unverified.

Example:
- `licence_status: valid — customer stated`
- `verification_status: pending`

## Rule 9 — Sensitive information
Do not turn sensitive customer statements into unsupported conclusions or guarantees. Route judgment-based cases appropriately.
