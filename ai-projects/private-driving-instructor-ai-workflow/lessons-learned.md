# Lessons Learned

## Workflow vs prompt
A prompt gives AI instructions. A workflow defines the complete process in which AI operates.

## AI as a component
AI should be treated as one component inside a business process, not as the entire process.

## Core architecture
**Input → Process → Decision → Action → Output**

For this project the operational sequence is:
**Input → Extract → Qualify → Validate → Decide → Action → Verify → Book → Output**

## Extraction vs validation
Extraction records what the customer said. Validation determines whether that information can be accepted for a business decision.

## Automation principle
The normal, defined path should be automated where appropriate. Human escalation should be a controlled exception path.

## Human-in-the-loop
Sensitive, conflicting, undefined, out-of-scope, or judgment-based situations should not be resolved by AI improvisation.

## Business rule principle
AI should apply approved business rules; it should not create new business policy when a rule is missing.

## Next improvements
- Map the workflow to actual automation tools.
- Define every input field and data type.
- Build a complete rule/decision table.
- Define payment verification integration.
- Define booking integration.
- Add privacy and data-retention controls.
- Build automated regression tests.
