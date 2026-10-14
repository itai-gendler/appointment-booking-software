---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member opens today's appointment and picks Waiting"
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Product saves the Appointment's progress"
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: changes, facts: [Progress] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Mark a client as waiting

## Trigger

A client arrives for today's appointment.

## Outcome

The calendar shows the appointment as waiting.

## Edge cases

- Requested appointments and appointments on a later day offer no progress.
