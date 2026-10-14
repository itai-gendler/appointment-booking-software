---
kind: edge
routes:
  web: Web
steps:
  - text: The Client chooses Book appointment on the summary
    kind: actor
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "The agent already has an Appointment then, so the Product refuses"
    kind: condition
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Duration] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
---

# Book a slot just taken

## Trigger

Someone else books the same agent at the same time first.

## Outcome

Nothing is booked; the page asks the client to choose a different appointment.
