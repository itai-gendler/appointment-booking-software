---
kind: edge
routes:
  web: Web
steps:
  - text: The Client chooses Book appointment on the summary
    kind: actor
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "No Member has access to client details, so the Product refuses new clients"
    kind: condition
    entities:
      - { entity: member, effect: reads, facts: [Access] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
---

# Book while no staff member has access

## Trigger

A new client books while nobody on the tenant's staff can read client details.

## Outcome

Nothing is booked; the booking fails.
