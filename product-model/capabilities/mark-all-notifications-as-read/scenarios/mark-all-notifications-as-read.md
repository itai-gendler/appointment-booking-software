---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Mark all as read
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::notifications
  - text: The Product removes every Notification of the Staff member
    kind: product
    actor: staff-member
    entities:
      - { entity: notification, effect: removes }
    contexts:
      web:
        place: web::dashboard::notifications
---

# Mark all notifications as read

## Trigger

A staff member caught up with everything.

## Outcome

No notifications are listed.
