---
kind: validation
routes:
  web: Web
steps:
  - text: "The Client chooses It's my first time here and sets a PIN"
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "A Client account already exists for the address, so the Product refuses and points to the login"
    kind: condition
    entities:
      - { entity: client, effect: reads, facts: [E-mail address] }
      - { entity: account, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
---

# Register an e-mail address already registered

## Trigger

A returning client chooses It's my first time here.

## Outcome

No account or appointment is created; the page asks them to use the login option.
