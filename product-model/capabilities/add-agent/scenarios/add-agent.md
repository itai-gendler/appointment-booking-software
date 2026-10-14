---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member enters the agent's name, an optional description and image, and adds it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::agents
  - text: The Product adds the Agent
    kind: product
    actor: staff-member
    entities:
      - { entity: agent, effect: creates, facts: [Name, Description, Image] }
    contexts:
      web:
        place: web::dashboard::agents
---

# Add an agent

## Trigger

A new colleague starts taking appointments.

## Outcome

The agent exists and can be added to channels.
