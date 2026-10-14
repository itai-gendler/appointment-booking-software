---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member deletes the absence and confirms
    kind: actor
    actor: staff-member
    entities:
      - { entity: absence, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
  - text: The Product deletes the Absence
    kind: product
    actor: staff-member
    entities:
      - { entity: absence, effect: removes }
    contexts:
      web:
        place: web::dashboard::absences
---

# Delete an absence

## Trigger

An agent's trip is cancelled.

## Outcome

The agent is offered again in that timespan.
