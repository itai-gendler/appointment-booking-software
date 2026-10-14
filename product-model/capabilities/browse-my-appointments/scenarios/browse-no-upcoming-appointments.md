---
kind: edge
routes:
  web: Web
steps:
  - text: The Client opens their appointments
    kind: actor
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::client-area::my-appointments
  - text: "No upcoming Appointment exists, so the Product offers to book one"
    kind: condition
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::client-area::my-appointments
---

# No upcoming appointments

## Trigger

A signed-in client has nothing booked ahead.

## Outcome

The page says so and offers to book an appointment.
