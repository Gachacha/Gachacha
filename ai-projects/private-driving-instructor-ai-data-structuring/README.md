# AI Customer Data Structuring

## Project 005

### Purpose
Design a reliable data layer that converts messy customer messages into structured information that an AI workflow can validate and use.

### Core pipeline
**Customer message → Extract → Structure → Preserve uncertainty → Verify → Qualify → Decide**

### Core principle
**Customer statement ≠ verified fact ≠ AI recommendation.**

AI should structure what the customer says without inventing missing facts or false precision.

### Structured customer fields
- `name`
- `licence_status`
- `driving_experience`
- `time_away_from_driving`
- `current_location`
- `destination`
- `training_objective`
- `package_selected`
- `package_recommendation`
- `verification_status`

### Data-quality principles
1. Preserve the customer's level of precision: "about 7 years" remains "about 7 years."
2. Missing information remains unknown; it is not guessed.
3. Uncertain information is marked uncertain and verified before important decisions.
4. Conflicting information is preserved as conflicting and resolved through clarification or verification.
5. Customer-selected information and AI-generated recommendations remain separate.
6. Structured data is not automatically verified data.

### Testing
The project was stress-tested against ambiguous, missing, conflicting, inferred, verification, sensitive, and uncertain customer information.

**Recall: 10/10**

**Build: 9/10**

**Stress test: 7/8**

### Relationship to earlier projects
Project 003 focused on the AI customer qualification component.

Project 004 designed the complete AI-assisted business workflow.

Project 005 builds the structured information layer that feeds reliable data into that workflow.
