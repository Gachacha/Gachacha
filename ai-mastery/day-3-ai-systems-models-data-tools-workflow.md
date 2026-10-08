# Day 3/180 — AI Systems: Models, Data, Tools, Workflow, and Humans

## Lesson Metadata
- Target lesson time: 120 minutes
- Capability stage: Thinking → Building
- Capability pyramid: Understanding → Building
- Curriculum stage: AI Systems
- Learning cycle: LEARN → RECALL → BUILD → TEST → DEPLOY → DOCUMENT → DEMONSTRATE → CLOSE

## Core Principle
> The model provides capability. The system provides control.

An AI system is not just a model. It is a coordinated system of models, data, tools, business rules, workflow/state, verification, monitoring and human responsibility.

## Controlled AI System Architecture
User Input → AI Model → Structured Data → Verification → Business Rules → Workflow / State Machine → Approved Action → External Tool → Verification → Human Responsibility when required

## Component Responsibilities

### AI Model — Capability
Interprets or generates information: natural-language understanding, extraction, classification, summarization, generation, pattern recognition and recommendations. It does not automatically know whether a claim is true, whether a booking succeeded, or whether it has authority to make a business decision.

### Data — Information
Controlled fields can include name, contact, licence information, vehicle access, location, driving need, objective, verification status, qualification status, booking status and process ID.
> Customer claim ≠ verified fact.

### External Tools — External Capability
Tools such as Google Calendar, Google Sheets, messaging, databases, calculators, maps/geolocation services and APIs perform external capabilities. A tool is not automatically AI.

### Business Rules — Authority
Approved rules determine what the business allows: qualification requirements, package catalogue, service radius, payment terms, booking conditions and escalation conditions.
> AI may recommend. Approved rules authorize.

### Workflow / State Machine — Process Control
The state machine controls where a case is in the process.
RECEIVED → VALIDATED → QUALIFICATION_PENDING_VERIFICATION → QUALIFIED → BOOKING_PENDING → BOOKED
If a result cannot be determined, an explicit UNKNOWN state should be used where appropriate.
> State = process condition. ID = traceability.

### Verification — Evidence
Verification establishes whether a fact, action or external result is actually confirmed.
Booking request → Calendar → Confirmation evidence → Verification → BOOKED
A request is not itself a confirmed result.

### Human Responsibility — Accountability
Humans define and approve rules, handle exceptions and conflicts, reconcile unknown results, make decisions outside AI authority, supervise the system and deliver the actual service.
> Automation does not eliminate responsibility.

### Monitoring — Reliability
Monitor incorrect extraction, unsupported claims, rule violations, verification failures, tool failures, duplicate actions, unexpected state transitions, repeated human intervention and unresolved UNKNOWN states.

### Documentation — System Understanding
Document purpose, inputs, outputs, model responsibility, data fields, tools, rules, states, verification, risks, monitoring, human responsibility and exception handling.

## Day 3 Build — PDI Example
James says: “Hi, I'm James. I recently got my licence but I'm nervous driving alone. I have my own car, live in Ruaka, and need to drive to my office in Westlands. Can you help me?”

System design:
1. AI interprets the natural-language message and structures relevant information.
2. Structured data records James's name, licence information, confidence need, vehicle access, location and commute objective.
3. Verification establishes required facts before qualification.
4. Business rules apply approved licence, vehicle, service-radius and qualification requirements.
5. Workflow/state controls James's current process state.
6. Approved action is performed only when authorized.
7. External tools perform approved actions such as calendar booking.
8. Final verification establishes whether the external action actually succeeded.
9. Human responsibility handles exceptions, conflicts, unknown outcomes and decisions outside AI authority.

## Build Risk and Control
Risk: AI could treat an unverified customer claim as a verified fact and incorrectly qualify the customer.
Control: Keep the information UNVERIFIED until required verification is completed, and prevent authoritative qualification until the approved requirement is satisfied.

## Recommendation vs Authority
An AI recommendation such as “James should receive Confidence Master” is an inference/recommendation. The system must apply approved rules and verify required facts before authorizing a pathway.

## Booking Timeout Control
If a booking request times out:
- State: BOOKING_STATUS_UNKNOWN
- Evidence: no confirmation evidence received
- Traceability: preserve the process/booking ID
- Next action: reconcile and verify before further booking action

Do not convert unknown into booked or failed without evidence.

## Durable System Boundaries
| Component | Primary responsibility |
|---|---|
| AI Model | Interpretation / generation |
| Data | Information |
| Business Rules | Authority |
| State Machine | Process control |
| External Tools | External capability |
| Verification | Evidence |
| Human | Responsibility |
| Monitoring | Reliability observation |
| Documentation | System understanding |

## Day 3 Recall Result
Ten multiple-choice recall questions completed.
**Score: 10/10 — 100%**

The user correctly distinguished model from system, AI interpretation from verification, extracted data from verified facts, tools from models, rules from recommendations, state from action, requests from confirmed results, UNKNOWN from failure, AI capability from AI authority, and human responsibility from automated capability.

## Day 3 Build Result
The user successfully assembled:
AI → Structured Data → Verification → Business Rules → State Machine → Approved Action → External Tool → Verification → Human Responsibility

One correction was required: “Confirmation” was initially supplied where “Approved Action” was required. The distinction was corrected:
- Approved Action = authorized action.
- Verification/confirmation evidence = evidence that the action succeeded.

**Build: PASSED**

## Day 3 Test Result
Five application scenarios completed.
**Score: 5/5 — 100%**

The user correctly applied service-radius checking, vehicle-access verification, external-tool confirmation, rejection of unsupported recommendations, and UNKNOWN-state reconciliation after timeout.

**Test: PASSED**

## Day 3 Status
- Learn: Complete
- Recall: 10/10 — 100%
- Build: Passed
- Test: 5/5 — 100%
- Deploy: Completed to GitHub
- Document: Completed
- Demonstrate: Pending final close demonstration
- Close: Pending final close demonstration

## Day 3 Practitioner Principles
> A model is one component of an AI system.
> The model provides capability. The system provides control.
> Rules = authority.
> State machine = process control.
> ID = traceability.
> Verification = evidence.
> Human = responsibility.
> AI recommendation ≠ authorized decision.
> Tool request ≠ confirmed result.
> Unknown must remain unknown until evidence resolves it.

## Next
Complete the final Day 3 Demonstrate phase by explaining the architecture and component boundaries without multiple-choice support. Then close Day 3 and carry the durable system-practitioner understanding into Day 4.
