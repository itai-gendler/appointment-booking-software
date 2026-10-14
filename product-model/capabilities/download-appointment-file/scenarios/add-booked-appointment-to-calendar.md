---
kind: primary
routes:
  web: Web
steps:
  - text: The Client chooses Add to Calendar after booking
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Product creates a calendar file of the Appointment
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Duration] }
    contexts:
      web:
        place: web::booking-site::book-appointment
---

# Add my appointment to my calendar

## Trigger

A client has just booked.

## Outcome

A calendar file with the appointment is downloaded, marked pending while confirmation is outstanding.
