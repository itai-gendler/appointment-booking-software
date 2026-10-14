---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member deselects the agent for the channel and saves
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: The Product removes the Agent from the Channel
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Agents] }
      - { entity: agent, effect: reads, facts: [Name] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Remove an agent from a channel

## Trigger

A colleague no longer serves a type of appointment.

## Outcome

Clients can no longer book that agent in the channel; appointments already booked stay.
