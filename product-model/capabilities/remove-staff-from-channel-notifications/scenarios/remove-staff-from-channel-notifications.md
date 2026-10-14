---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member deselects a colleague among the staff the channel notifies and saves
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: "The Product removes the Member from the Channel's notified staff"
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Notified staff] }
      - { entity: member, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Stop notifying a staff member about a channel

## Trigger

A staff member hands a channel over.

## Outcome

They no longer receive the channel's notifications.
