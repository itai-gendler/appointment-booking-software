---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member edits the agent's name, description or image and saves"
    kind: actor
    actor: staff-member
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::agents
  - text: The Product saves the Agent
    kind: product
    actor: staff-member
    entities:
      - { entity: agent, effect: changes, facts: [Name, Description, Image] }
    contexts:
      web:
        place: web::dashboard::agents
---

# Edit an agent

## Trigger

An agent's title changes.

## Outcome

Clients see the new details when choosing whom to book with.
