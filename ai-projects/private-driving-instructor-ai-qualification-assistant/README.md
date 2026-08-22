# Private Driving Instructor AI Qualification Assistant

## Project 003
**Status: Prototype / deployed for portfolio documentation**

## Problem
Customer enquiries require time to read, extract information, qualify the customer, and determine the appropriate next step.

## Solution
An AI-assisted customer qualification prompt that receives customer messages, extracts relevant information, identifies missing information, validates where approved methods exist, checks approved business rules, determines status, recommends an approved next action, and escalates cases requiring human judgment.

## Design philosophy
AI assists within defined boundaries. It does not replace the instructor's judgment or invent business policy.

## Prompt architecture
**ROLE → OBJECTIVE → CONTEXT → RULES → INPUT → PROCESS → OUTPUT**

## Core rules
- Use approved business information only.
- Never invent prices, packages, eligibility requirements, terms, or exceptions.
- If required information is missing, ask an approved qualifying question.
- If information conflicts, do not guess. Clarify or escalate.
- Payment claims are not treated as verified without the approved verification method.
- Sensitive or undefined situations are escalated to a human.
- Do not make unsupported guarantees.
- Stay within the defined business scope.

## Testing
The prompt was stress-tested against nine scenarios:
1. Missing information
2. Customer attempting to bypass eligibility rules
3. Prompt injection / instruction override
4. Conflicting information
5. Unverified payment
6. Sensitive situation and unsupported guarantee
7. Unapproved business information
8. Out-of-scope request
9. Normal qualified customer

**Result: 9/9 tests passed.**

## Human role
The human instructor remains responsible for driving instruction, sensitive matters, complex objections, undefined exceptions, conflicting cases requiring judgment, and other decisions outside approved rules.

## Limitations
This is a prompt/workflow prototype, not a production automation. It requires finalized package rules, approved qualifying questions, approved answers, terms, exception rules, payment verification, booking integration, and ongoing testing before live customer use.

## Builder Scholar cycle
- Learn: Complete
- Recall: 8/10
- Build: Complete
- Test: 9/9 passed
- Deploy: Complete
- Document: In progress
- Demonstrate: Pending
- Close: Pending
