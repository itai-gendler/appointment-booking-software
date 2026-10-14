---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member types the channel's name to confirm and deletes it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channels
  - text: The Product deletes the Channel with its schedule
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: removes, from: Active }
    contexts:
      web:
        place: web::dashboard::channels
---

# Delete a channel

## Trigger

A type of appointment is discontinued for good.

## Outcome

The channel is gone from the channels list and the booking site.

## Edge cases

- A deactivated channel is deleted the same way.
