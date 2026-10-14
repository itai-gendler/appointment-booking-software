---
kind: edge
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
  - text: "No Appointment needs a reminder, so the Product sends none"
    kind: condition
    entities:
      - { entity: appointment, effect: reads, facts: [Reminder sent] }
    contexts:
      web:
        place: web::dashboard::home
---

# Nothing to remind

## Trigger

No appointment until tomorrow evening needs a reminder.

## Outcome

The card says there are no reminders to send.
