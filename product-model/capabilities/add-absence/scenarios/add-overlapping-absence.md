---
kind: validation
routes:
  web: Web
steps:
  - text: "The Staff member picks the agent and a period, and adds a one-time absence"
    kind: actor
    actor: staff-member
    entities:
      - { entity: absence, effect: reads, facts: [] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
  - text: "Another one-time Absence of the Agent overlaps the period, so the Product refuses"
    kind: condition
    entities:
      - { entity: absence, effect: reads, facts: [Start, End] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
---

# Add an overlapping absence

## Trigger

A staff member adds a one-time absence in a period the agent is already absent.

## Outcome

No absence is added; the form says the agent is already (partially) absent then.
