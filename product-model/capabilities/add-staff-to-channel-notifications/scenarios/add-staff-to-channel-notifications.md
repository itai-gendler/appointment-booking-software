---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member selects a colleague among the staff the channel notifies and saves
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: "The Product adds the Member to the Channel's notified staff"
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Notified staff] }
      - { entity: member, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Notify a staff member about a channel

## Trigger

A staff member takes over a channel's requests.

## Outcome

They receive the channel's notifications from now on.
