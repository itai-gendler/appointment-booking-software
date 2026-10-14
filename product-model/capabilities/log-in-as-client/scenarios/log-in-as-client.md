---
kind: primary
routes:
  web: Web
steps:
  - text: The Client enters their e-mail address and PIN
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::client-login
  - text: "The Product proves the PIN on the Client's device and signs the Client in"
    kind: product
    actor: client
    entities:
      - { entity: client, effect: reads, facts: [E-mail address, PIN] }
    contexts:
      web:
        place: web::booking-site::client-login
  - text: "The Product opens the Client's appointments"
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::client-login
---

# Log in with e-mail address and PIN

## Trigger

A client wants to see or cancel their appointments.

## Outcome

The client is signed in and sees their upcoming appointments.
