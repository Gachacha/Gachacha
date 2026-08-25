# Lessons Learned

## 1. Unstructured data
Human messages such as WhatsApp enquiries are unstructured data.

## 2. Structured information
A schema converts relevant parts of a message into consistent fields that a workflow can use.

## 3. Preserve uncertainty
AI must not turn vague statements into precise facts.

Examples:
- "about 7 years" → `about 7 years`
- "many years" → `many years`, not an invented number
- "I think my licence is valid" → `uncertain — requires verification`

## 4. Missing data
Missing information stays unknown until it is obtained. It is not guessed.

## 5. Data is not automatically truth
Structured data can still be unverified. Verification status should be kept separate.

## 6. Customer data vs AI output
The customer's selected package and the AI's package recommendation are different fields and must not be confused.

## 7. Extraction vs qualification
Extraction organizes what the customer said. Qualification applies business rules to determine what the business should do.

## Core principle
**Customer statement ≠ verified fact ≠ AI recommendation.**

## Next development
The next project can build on this data layer by connecting structured information to decision tables and automation logic.
