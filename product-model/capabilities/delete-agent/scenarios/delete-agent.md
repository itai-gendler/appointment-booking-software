---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member types the agent's name to confirm and deletes it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::agents
  - text: The Product deletes the Agent and takes it off its channels
    kind: product
    actor: staff-member
    entities:
      - { entity: agent, effect: removes }
      - { entity: channel, effect: changes, facts: [Agents] }
    contexts:
      web:
        place: web::dashboard::agents
---

# Delete an agent

## Trigger

A colleague leaves the organization.

## Outcome

The agent is gone from the agents list and from every channel.
