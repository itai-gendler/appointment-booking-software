---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member selects the channel's first agent and saves"
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: The Product adds the Agent and moves the Tenant on to its staff step
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Agents] }
      - { entity: tenant, effect: changes, from: Awaiting channel, to: Awaiting staff, facts: [] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Complete the first channel before staff joins

## Trigger

The first channel already has a schedule, gets its first agent, and nobody has joined the tenant's staff yet.

## Outcome

The channel step is done; the onboarding guide moves on to staff.
