---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin chooses Unselect tenant in the tenant switcher
    kind: actor
    actor: global-admin
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard
  - text: "The Product clears the Global Admin's selected tenant"
    kind: product
    actor: global-admin
    entities:
      - { entity: global-admin, effect: changes, facts: [Selected tenant] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard
---

# Unselect the tenant

## Trigger

A global admin is done with a tenant.

## Outcome

No tenant is selected; tenant pages are hidden until one is selected again.
