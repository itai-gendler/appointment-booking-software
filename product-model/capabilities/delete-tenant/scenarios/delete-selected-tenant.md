---
kind: validation
routes:
  web: Web
steps:
  - text: The Global Admin chooses Delete on the tenant they are managing
    kind: actor
    actor: global-admin
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::administration::tenants
  - text: "It is the Global Admin's selected tenant, so the Product refuses to delete it"
    kind: condition
    entities:
      - { entity: global-admin, effect: reads, facts: [Selected tenant] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::administration::tenants
---

# Delete the selected tenant

## Trigger

A global admin tries to delete the tenant they are currently managing.

## Outcome

The tenant stays; the page asks them to switch to another tenant first.
