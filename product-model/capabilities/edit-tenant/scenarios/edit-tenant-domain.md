---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin enters the new domain and saves
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::administration::tenants
  - text: "The Product saves the Tenant's domain"
    kind: product
    actor: global-admin
    entities:
      - { entity: tenant, effect: changes, facts: [Domain] }
    contexts:
      web:
        place: web::administration::tenants
---

# Change a tenant's domain

## Trigger

A tenant moves to another address.

## Outcome

The tenant's booking site and dashboard are reached at the new domain.

## Edge cases

- A domain another tenant uses is refused.
