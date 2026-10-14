---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member opens the dashboard home
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::home
  - text: "The Product finds confirmed appointments until tomorrow evening, not booked today, not yet reminded, whose client wishes updates"
    kind: condition
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Booked at, Reminder sent, E-mail updates, Name, E-mail address, Language] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::home
  - text: The Product e-mails each reminder and records it on the Appointment
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: changes, facts: [Reminder sent] }
    contexts:
      web:
        place: web::dashboard::home
---

# Send reminders on opening the dashboard

## Trigger

A staff member starts the day on the dashboard.

## Outcome

Clients with an appointment until tomorrow evening have their reminder; the card says how many were sent.
