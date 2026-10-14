---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member tries to log in again
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::login
  - text: "Too many attempts failed, so the Product refuses until the waiting time is over"
    kind: condition
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Log in after repeated failures

## Trigger

Several login attempts for one e-mail address have failed in a row.

## Outcome

Further attempts are refused for a while and the person is told when to retry.
