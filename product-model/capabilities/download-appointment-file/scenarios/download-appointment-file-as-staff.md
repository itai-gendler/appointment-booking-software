---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Download as file on an appointment
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product creates a calendar file of the Appointment
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Duration, Name] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Download an appointment as staff

## Trigger

A staff member wants an appointment in their own calendar.

## Outcome

A calendar file with the appointment is downloaded.
