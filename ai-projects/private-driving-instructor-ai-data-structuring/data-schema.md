# Customer Data Schema

## Purpose
Define the fields AI should extract from customer enquiries.

| Field | Meaning | Example |
|---|---|---|
| `name` | Customer's stated name | Jane |
| `licence_status` | Licence status as stated, with uncertainty preserved | valid / uncertain |
| `driving_experience` | Customer's stated driving experience | about 7 years |
| `time_away_from_driving` | Time since regular driving, preserving uncertainty | almost 2 years |
| `current_location` | Where the customer is currently based | Nairobi |
| `destination` | Main driving destination | Westlands |
| `training_objective` | What the customer wants to achieve | drive to work |
| `package_selected` | Package explicitly selected by customer | none |
| `package_recommendation` | Package recommended by workflow | pending |
| `verification_status` | Whether important claims have been verified | pending |

## Data-state distinction

A field may have separate states such as:
- stated
- unknown / not provided
- uncertain
- conflicting
- verified
- AI-generated recommendation

## Example

Customer message:
> "I've been driving for about 8 years, but I haven't driven since sometime in 2023. I think my licence is still valid. I want to drive to work in Westlands."

Structured representation:

```text
name: unknown
licence_status: uncertain — requires verification
driving_experience: about 8 years
time_away_from_driving: sometime since 2023 — exact duration unknown
current_location: unknown
destination: Westlands
training_objective: drive to work
package_selected: none
package_recommendation: pending
verification_status: licence pending
```
