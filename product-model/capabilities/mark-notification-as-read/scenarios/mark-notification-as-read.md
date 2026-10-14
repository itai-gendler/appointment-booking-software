---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Mark as read on a notification
    kind: actor
    actor: staff-member
    entities:
      - { entity: notification, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::notifications
  - text: The Product removes the Notification
    kind: product
    actor: staff-member
    entities:
      - { entity: notification, effect: removes }
    contexts:
      web:
        place: web::dashboard::notifications
---

# Mark a notification as read

## Trigger

A staff member has dealt with a notification.

## Outcome

The notification is no longer listed.
