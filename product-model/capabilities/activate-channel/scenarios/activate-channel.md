---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Activate Channel and confirms
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: The Product activates the Channel
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, from: Deactivated, to: Active, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Activate a channel

## Trigger

A suspended type of appointment resumes.

## Outcome

The channel offers and accepts new appointments again.
