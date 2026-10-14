---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Add follow-up on an appointment
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, as: earlier, effect: reads, facts: [Name, E-mail address, Phone number] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The calendar shows only available slots
    kind: condition
    entities: []
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Staff member chooses a free slot and confirms with the client's details already filled in"
    kind: actor
    actor: staff-member
    entities:
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product books the follow-up Appointment for the same Client
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, as: follow-up, effect: creates, to: Confirmed, facts: [Date and time, Duration, Time zone, Name, E-mail address, Phone number, Language, E-mail updates, Progress, Booked at] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Add a follow-up appointment

## Trigger

At the end of an appointment the client needs another one.

## Outcome

A second confirmed appointment exists for the same client.
