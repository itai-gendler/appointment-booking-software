---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member opens Add Absence
    kind: actor
    actor: staff-member
    entities:
      - { entity: absence, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
  - text: "No Agent exists, so the Product asks for an agent first"
    kind: condition
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
---

# Add an absence with no agents

## Trigger

A staff member opens Add Absence before the tenant has any agent.

## Outcome

Nothing can be added; the page says an agent must be added first.
