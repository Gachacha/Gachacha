# MUMBI AI MASTERY — DAY 1/180

## AI Foundations: From AI User to AI Practitioner

- Lesson: 1/180
- Target lesson time: 120 minutes
- Current level: Beginner — Foundation Reset
- Capability stage: Thinking → Building → Integrating
- AI capability pyramid: Foundation → Understanding → Building → Integrating

## Current curriculum

AI Literacy → AI Application → AI Systems → AI Evaluation → AI Assurance → AI Deployment → AI Training

Prompt engineering is a supporting skill, not the center of the programme.

## Practitioner lens

Task → Risk → Model → Data → Tools → Evaluation → Monitoring → Human Responsibility → Documentation

## Learning cycle

LEARN → RECALL → BUILD → TEST → DEPLOY → DOCUMENT → DEMONSTRATE → CLOSE

## Day 1 training scope

1. AI is a broad field, not ChatGPT.
2. Machine learning is one major approach to AI.
3. An AI model is a trained computational engine.
4. An LLM is one type of AI model focused on language.
5. A model is not a complete AI system.
6. Tools provide external capabilities and are not automatically AI.
7. Automation does not require AI.
8. AI capability does not equal AI authority.
9. Facts, inferences and decisions must be distinguished.
10. Workflow states represent confirmed process conditions.
11. Unknown is a valid state when an external result has not been verified.
12. Controlled AI systems combine models, structured facts, rules, workflow, tools, verification and human responsibility.

## Core architecture

Client/User Input
→ AI Interpretation
→ Structured Facts
→ Business Rules
→ Workflow/State
→ Approved Action
→ External Tool
→ Verification
→ Result

## Day 1 practical build — PDI client qualification system

### Task
Extract customer information → verify it against approved rules → qualify the client.

### Risks identified
- Do not invent missing information.
- Do not book without following the approved pathway.

### Model
Use an AI language model to understand the client's language, need, objective and clarify the enquiry.

### Data
- Full names
- Licence status
- Whether the client has a car for practice
- Location
- Need
- Objective

Important control: client-reported information must be distinguished from verified information.

### Tools
- WhatsApp
- Make
- Google Drive
- Calendar

Make is the automation/orchestration layer, not the AI model.

### Evaluation
Test whether the system:
- extracts information correctly,
- distinguishes reported from verified information,
- qualifies against approved rules,
- follows the approved pathway after verified steps.

### Monitoring
Monitor for:
- incorrect workflow transitions,
- unsupported or invented claims,
- tool/automation failures,
- repeated human-review cases,
- duplicate or unexpected actions.

### Human responsibility
The human remains responsible for:
- defining and approving business rules,
- delivering the services,
- handling exceptions such as double bookings,
- decisions outside the AI's approved authority.

### Documentation
Document:
- system purpose,
- approved business rules,
- workflow states,
- guardrails,
- data fields.

## Deployment design

Client enquiry
→ Extract information
→ Verify information
→ Apply approved business rules
→ Qualify
→ Customer selects/confirm an approved package
→ Initiate booking request
→ BOOKING_PENDING
→ External booking result
→ Verify/reconcile result
→ BOOKED if confirmed
→ BOOKING_STATUS_UNKNOWN if outcome cannot be determined
→ Recovery/escalation according to approved rules

Important distinction:

**Booking request ≠ confirmed booking.**

A timeout does not prove success or failure. Use an UNKNOWN state and reconcile using the relevant process/booking ID.

## Day 1 recall

- Recall score: 10/10
- Result: Passed

## Day 1 test

- Test score: 8/10
- Result: Passed with identified gaps

### Test gaps identified
1. Timeout handling: initially selected BOOKING_PENDING; correct controlled state when the result cannot be determined is BOOKING_STATUS_UNKNOWN.
2. State vs confirmed result: reinforced that an attempted action is not the same as a confirmed workflow state.

## Day 1 build and deployment status

- Build: Passed
- Conceptual deployment: Passed
- Documentation: Updated during lesson
- Demonstration: Pending
- Close: Pending

## Mastery standard

Recall alone does not prove mastery. The learner must demonstrate understanding through application, building, testing, deployment, documentation and demonstration.

## Restart note

This file represents the clean Day 1/180 restart under the updated MUMBI practitioner curriculum. Previous Day 1–20 work remains revision/reference material and is not treated as current mastery evidence.
