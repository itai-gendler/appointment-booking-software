---
kind: primary
routes:
  web: Web
steps:
  - text: The Client chooses Log out
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::client-area::my-appointments
  - text: "The Product forgets the Client's sign-in and returns to the home page"
    kind: product
    actor: client
    entities: []
    contexts:
      web:
        place: web::client-area::my-appointments
---

# Log out of my appointments

## Trigger

A client has checked their appointments.

## Outcome

The client is signed out and back on the home page.
