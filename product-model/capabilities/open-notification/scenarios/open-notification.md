---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member opens their notifications and selects one
    kind: actor
    actor: staff-member
    entities:
      - { entity: notification, effect: reads, facts: [Kind] }
    contexts:
      web:
        place: web::dashboard::notifications
  - text: "The Product opens the calendar on the Appointment's day with its details"
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Open a notification

## Trigger

A staff member sees a new appointment request among their notifications.

## Outcome

The calendar shows the day of that appointment with its details open.
