---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member enters the channel's name and description and adds it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channels
  - text: The Product adds the Channel with the next calendar color
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: creates, to: Active, facts: [Name, Description, Color] }
    contexts:
      web:
        place: web::dashboard::channels
---

# Add a channel

## Trigger

The organization starts offering a new type of appointment.

## Outcome

The channel exists, marked incomplete until it has agents and a schedule.
