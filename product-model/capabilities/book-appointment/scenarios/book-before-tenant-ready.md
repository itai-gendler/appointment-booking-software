---
kind: edge
routes:
  web: Web
steps:
  - text: The Client opens the home page
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::home
  - text: "The Tenant is not ready, so the Product offers no booking"
    kind: condition
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::home
---

# Visit a tenant that is not ready

## Trigger

A client opens the booking site of a tenant still being set up.

## Outcome

No appointment can be booked; the home page says the tenant is not ready to accept appointments.
