# Private Driving Instructor AI Customer Workflow

## Project status
**Prototype specification | Project 002 | Builder Scholar journey**

## Problem
Customer enquiries require instructor time to read, extract information, qualify the customer, answer questions, and determine the appropriate next step.

## Objective
Design an AI-assisted workflow that can process customer enquiries, extract and qualify information, ask approved qualifying questions, apply approved business rules, identify exceptions, and hand off situations requiring human judgment.

## Core workflow
**INPUT → PROCESS → VALIDATE → DECIDE → OUTPUT → ACTION → HUMAN HANDOFF**

### AI responsibilities
- Extract customer information
- Classify enquiries
- Identify missing information
- Ask approved qualifying questions
- Apply approved eligibility rules
- Provide approved information
- Identify exceptions and conflicts
- Escalate sensitive or undefined situations

### Human responsibilities
- Driving instruction
- Sensitive customer situations
- Complex objections
- Decisions outside approved rules
- Professional judgment
- Exceptional cases without approved rules

## Key design principles
- **EXTRACT ≠ VERIFY**
- Do not guess when required information is missing
- AI must operate from approved business rules
- AI must not invent business policy
- Conflicting or ambiguous information requires clarification or human review
- Payment claims must be verified before booking

## Testing
The workflow was tested against six failure scenarios:

1. Missing information
2. Conflicting information
3. Unsupported customer claims
4. Exceptions outside approved rules
5. Sensitive/high-risk situations
6. Unverified payment

**Result: 6/6 tests passed.**

## Current limitations
This repository documents a validated workflow design and prototype specification. It is not yet a production automation. Formal package eligibility rules, approved questions, approved answers, exception rules, payment verification, and booking integration still need to be defined before live deployment.

## Builder Scholar cycle
- Learn: Complete
- Recall: 10/10
- Build: Complete
- Test: 6/6 passed
- Deploy: Repository published
- Document: In progress
- Demonstrate: Pending
- Close: Pending
