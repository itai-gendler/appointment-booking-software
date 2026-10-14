---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member picks the agent, One-Time, a reason and the period, and adds it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
  - text: The Product adds the Absence for the Agent and frees no more slots in that period
    kind: product
    actor: staff-member
    entities:
      - { entity: absence, effect: creates, facts: [Kind, Reason, Start, End] }
      - { entity: agent, effect: reads, facts: [Name] }
    contexts:
      web:
        place: web::dashboard::absences
---

# Add a one-time absence

## Trigger

An agent goes on vacation.

## Outcome

No slots are offered for the agent during the period.

## Edge cases

- All day marks whole days.
