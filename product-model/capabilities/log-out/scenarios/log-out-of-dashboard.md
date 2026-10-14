---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Log out
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard
  - text: The Product ends the session and confirms the logout
    kind: product
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard
---

# Log out of the dashboard

## Trigger

A staff member is done for the day.

## Outcome

Their session has ended and the page offers to go to login.
