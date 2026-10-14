---
kind: primary
routes:
  web: Web
steps:
  - text: "The Product lists the Client's upcoming Appointment entries, decrypted on the device"
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Name] }
      - { entity: channel, effect: reads, facts: [Name] }
    contexts:
      web:
        place: web::client-area::my-appointments
  - text: "The Client reads the date, type and status of each appointment"
    kind: actor
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time] }
    contexts:
      web:
        place: web::client-area::my-appointments
---

# See my upcoming appointments

## Trigger

A client signed in to check their appointments.

## Outcome

They see each upcoming appointment with its type, time and status.
