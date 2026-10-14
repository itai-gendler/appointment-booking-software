---
kind: validation
routes:
  web: Web
steps:
  - text: The Client enters their e-mail address and a wrong PIN
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::client-login
  - text: "The PIN does not match, so the Product reports that the login failed"
    kind: condition
    entities: []
    contexts:
      web:
        place: web::booking-site::client-login
---

# Log in with a wrong PIN

## Trigger

A client mistypes their PIN.

## Outcome

The client is not signed in and is asked to retry.
