---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member selects another agent for the channel and saves
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: The Product adds the Agent to the Channel
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Agents] }
      - { entity: agent, effect: reads, facts: [Name] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Add an agent to a channel

## Trigger

A colleague starts serving a type of appointment.

## Outcome

Clients can book that agent in the channel.
