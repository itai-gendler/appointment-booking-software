---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member enters street, number, ZIP code and city and saves"
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::address-settings
  - text: "The Product saves the Tenant's visitor address"
    kind: product
    actor: staff-member
    entities:
      - { entity: tenant, effect: changes, facts: [Visitor address] }
    contexts:
      web:
        place: web::dashboard::address-settings
---

# Change the visitor address

## Trigger

The organization moves.

## Outcome

Appointment information for clients carries the new address.
