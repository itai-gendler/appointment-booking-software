---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Cancel Appointment and confirms
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product deletes the Appointment and frees its slot
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: removes, from: Confirmed }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product e-mails the cancellation when the client wishes updates
    kind: product
    actor: staff-member
    entities:
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Cancel an appointment as staff

## Trigger

An agent falls ill and the appointment cannot take place.

## Outcome

The appointment is gone and its slot is free; the client is told if they wished e-mails.
