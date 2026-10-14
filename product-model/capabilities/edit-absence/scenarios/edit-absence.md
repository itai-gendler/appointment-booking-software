---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member changes the absence's reason, period, weekdays or time window and saves"
    kind: actor
    actor: staff-member
    entities:
      - { entity: absence, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
  - text: The Product saves the Absence
    kind: product
    actor: staff-member
    entities:
      - { entity: absence, effect: changes, facts: [Kind, Reason, Start, End, Weekdays, Time window] }
    contexts:
      web:
        place: web::dashboard::absences
---

# Edit an absence

## Trigger

An agent's vacation is extended.

## Outcome

Slots follow the updated absence.

## Edge cases

- A period overlapping another one-time absence of the agent is refused.
