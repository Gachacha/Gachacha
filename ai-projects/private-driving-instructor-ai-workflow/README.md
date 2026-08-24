# AI Customer Enquiry Workflow

## Project 004
**Status: Prototype / deployed for portfolio documentation**

## Purpose
Design the complete business workflow in which AI assists with private-driving-instructor customer enquiries.

## Business problem
Customer enquiries require time to read, extract information, qualify, validate, decide, respond, verify payment, and coordinate booking.

## Solution
A controlled workflow that separates AI tasks, business rules, decisions, actions, verification points, and human escalation.

## Core architecture
**INPUT → EXTRACT → QUALIFY → VALIDATE → DECIDE → ACTION → VERIFY → BOOK → OUTPUT**

Human escalation is available for sensitive, conflicting, undefined, out-of-scope, or judgment-based situations.

## Key principle
**AI handles defined work. Humans handle judgment.**

## AI's role
AI can extract and structure information, ask approved qualifying questions, check approved rules, communicate approved recommendations, and route cases according to the workflow.

## Human's role
The human instructor handles sensitive matters, undefined exceptions, conflicting cases requiring judgment, and decisions outside approved rules.

## Relationship to Project 003
Project 003 focused on the **AI prompt** that operates within the process.

Project 004 focuses on the **whole workflow** in which AI operates.

**Prompt = AI instructions**

**Workflow = entire process**

## Validation principle
Customer claims must not automatically become verified business facts. Payment, eligibility, and other important claims require the approved validation method.

## Testing
The workflow was stress-tested against seven scenarios:
1. Normal qualified customer
2. Missing information
3. Exception request
4. Unverified payment
5. Conflicting information
6. Sensitive situation
7. Out-of-scope request

**Result: 7/7 tests passed.**

## Limitations
This is a workflow prototype, not a live production automation. Before live deployment, the business needs finalized rules, approved questions and responses, exception handling, payment verification, booking integration, data/privacy controls, and regression testing.
