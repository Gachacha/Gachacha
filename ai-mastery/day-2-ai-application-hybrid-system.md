# Day 2/180 — AI Application: Turning a Business Problem Into an AI System

## Lesson Metadata

- Target lesson time: 120 minutes
- Capability stage: Thinking → Building
- Capability pyramid: AI Application
- Curriculum stage: AI Application
- Learning cycle: LEARN → RECALL → BUILD → TEST → DEPLOY → DOCUMENT → DEMONSTRATE → CLOSE

## Core Principle

Not every business problem should be solved with AI.

A practitioner starts with:

> What is the actual business problem?

Then asks:

> Does AI belong in the solution?

Then:

> Where exactly should AI be used?

### Practitioner rule

> Use AI where interpretation or probabilistic capability creates value. Use deterministic software where deterministic logic is sufficient.

## Business Problem

For the PDI client enquiry system:

> Potential client enquiries take time to understand, structure, qualify and route correctly.

## Process Decomposition

Customer message
→ AI interpretation and extraction
→ Structured data
→ Verification
→ Approved business rules
→ Qualification
→ Approved action
→ External tool
→ Verification
→ Booked / Unknown / Human escalation

## AI vs Deterministic Boundary

### AI is appropriate for

- Understanding free-form customer messages
- Extracting information from natural language
- Interpreting driving goals and needs
- Classifying customer intent
- Identifying potentially missing information
- Assisting with natural-language responses

### Deterministic software is appropriate for

- Fixed business rules
- Service-radius calculations
- Package catalogue checks
- Price calculations
- Payment calculations
- Record storage
- Unique IDs
- Workflow/state transitions
- Permissions
- Controlled actions

### External tools

External systems perform actions such as calendar operations. Their results must be verified before the workflow records a confirmed outcome.

## Structured Client Record Example

Source message:

> “Hi, I'm Sarah. I have a valid Kenyan licence and my own Toyota. I live in Ruaka and want help becoming confident driving to work in Nairobi.”

Controlled extraction:

- Name: Sarah
- Licence status: Customer claims valid
- Vehicle: Toyota
- Location: Ruaka
- Driving goal: Driving confidence
- Client need: Driving to work
- Verification status: Unverified
- Qualification status: Pending required verification

Important distinction:

> Customer claim ≠ verified fact.

AI must not silently upgrade an unverified claim into a verified fact.

## AI Fit Test

For each task, ask:

1. Is the input unstructured?
2. Does the task require interpretation?
3. Can a deterministic rule solve it reliably?
4. What happens if AI is wrong?
5. Can the output be verified?
6. Does the AI actually have authority to make the decision?

## Controls

### Rules = Authority

Approved business rules define what the system is allowed to accept, reject, qualify or route.

AI cannot create, change or override those rules.

### Verification = Evidence

Verification establishes whether a required fact or external result is confirmed.

### State Machine = Process Control

Workflow states represent the confirmed process condition.

Example:

RECEIVED
→ VALIDATED
→ QUALIFICATION_PENDING_VERIFICATION
→ QUALIFIED
→ BOOKING_PENDING
→ BOOKED

If a result cannot be determined, use an explicit UNKNOWN state where appropriate.

### ID = Traceability

Unique IDs allow the system to trace a transaction, reconcile an unknown result and investigate exceptions.

### Human = Responsibility

Human responsibility remains for:

- exceptions outside approved rules,
- conflicting information,
- sensitive cases,
- consequential decisions outside AI authority,
- unresolved external results,
- actual service delivery.

## Build Result

The Day 2 hybrid architecture was designed as:

Customer Message
→ AI Interpretation
→ Structured Data
→ Verification
→ Business Rules
→ Qualification
→ Approved Action
→ External Tool
→ Verification
→ Booked / Unknown / Human

### Key build insight

AI should not be inserted into every stage simply because it can perform many tasks.

The practitioner decides the AI boundary based on:

- business value,
- task characteristics,
- risk,
- verification,
- authority.

## Test Result

Five application scenarios were tested.

### Result

**5/5 — 100%**

The user correctly handled:

1. AI recommendation versus authorized decision.
2. Out-of-radius service rules.
3. Booking timeout and UNKNOWN state.
4. AI inference versus approved requirements.
5. Required verification unavailable.

## Day 2 Core Understanding

The user demonstrated the ability to distinguish:

- business problem from AI solution,
- AI interpretation from deterministic control,
- customer claims from verified facts,
- inference from authority,
- process state from action,
- booking request from confirmed booking,
- unknown from failure,
- AI capability from AI authority.

## Deployment Specification

### Component 1 — AI Interpretation Layer

Purpose:
- Read natural-language enquiries.
- Extract structured fields.
- Identify intent, need and potentially missing information.

Constraint:
- No authority to invent facts, alter rules or authorize unsupported decisions.

### Component 2 — Structured Data Layer

Stores controlled fields such as:

- name
- contact
- licence claim/status
- vehicle access
- location
- need
- objective
- verification status
- qualification status
- booking status
- process ID

### Component 3 — Verification Layer

Confirms required facts before qualification or other controlled transitions.

### Component 4 — Business Rules Layer

Applies only approved business rules.

Examples:
- approved package catalogue,
- service-radius rules,
- qualification requirements,
- payment terms,
- booking conditions.

### Component 5 — Workflow/State Layer

Controls process progression.

AI does not directly set authoritative workflow states.

### Component 6 — Tool Layer

External tools may include:

- calendar
- messaging
- spreadsheet/database
- payment or other approved business tools

External tool results require verification.

### Component 7 — Monitoring Layer

Monitor for:

- unsupported AI claims,
- rule violations,
- verification failures,
- tool failures,
- repeated human intervention,
- duplicate actions,
- unexpected state transitions.

### Component 8 — Human Responsibility Layer

Humans retain responsibility for exceptions, unresolved cases and decisions outside the approved AI authority.

## Deployment Guardrail

The system must never convert:

- claim → verified fact,
- inference → authorized decision,
- request → confirmed action,
- unknown → success,
- missing information → rejection,

without the appropriate verification, rule or human decision.

## Day 2 Status

- Learn: Complete
- Recall: 10/10
- Build: Passed
- Test: 5/5 — 100%
- Deploy: Specification completed
- Document: This file
- Demonstrate: Pending
- Close: Pending

## Practitioner Principle

> AI is a capability inside a controlled system. It is not the authority of the system.

## Next

Demonstrate the architecture without prompts or multiple-choice support, then close Day 2 and record the durable lessons for the next stage.
