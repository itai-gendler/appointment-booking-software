---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member opens the link and claims the account
    kind: actor
    actor: staff-member
    entities:
      - { entity: account, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: "The link is wrong, used or expired, so the Product reports that verification failed"
    kind: condition
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::email-verification
---

# Open a wrong or outdated link

## Trigger

A person opens a confirmation link that is wrong, already used or expired.

## Outcome

Nothing is confirmed; the page says verification failed and offers to request a new e-mail.
