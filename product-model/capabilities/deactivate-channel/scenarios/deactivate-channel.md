---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Deactivate Channel and confirms
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: The Product deactivates the Channel
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, from: Active, to: Deactivated, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Deactivate a channel

## Trigger

A type of appointment is suspended for a while.

## Outcome

No new appointments are offered or accepted in the channel; existing ones stay.
