---
kind: edge
routes:
  web: Web
steps:
  - text: The Client tries their PIN again
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::client-login
  - text: "Too many attempts failed, so the Product asks the Client to wait a few minutes"
    kind: condition
    entities:
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::client-login
---

# Log in after repeated wrong PINs

## Trigger

A client has entered wrong PINs several times in a row.

## Outcome

Further attempts are refused for a while and the client is told when to retry.
