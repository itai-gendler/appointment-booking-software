---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member picks a slot and confirms the move
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The agent is booked or absent then, so the Product refuses the move"
    kind: condition
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Duration] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Move to a slot just taken

## Trigger

The chosen slot was taken meanwhile.

## Outcome

The appointment stays where it was; the page says the move failed.
