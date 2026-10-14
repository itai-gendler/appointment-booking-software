---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member adds the channel's first slot template and saves"
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel-schedule
  - text: The Product saves the schedule and marks the Tenant ready
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Schedule] }
      - { entity: tenant, effect: changes, from: Awaiting channel, to: Ready, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel-schedule
---

# Complete the first channel

## Trigger

A tenant's first active channel has an agent and gets its first schedule, and a staff member has already joined.

## Outcome

The tenant is ready: its booking site starts offering the channel.
