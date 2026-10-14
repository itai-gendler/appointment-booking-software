---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin picks another tenant in the tenant switcher
    kind: actor
    actor: global-admin
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard
  - text: "The Product makes it the Global Admin's selected tenant"
    kind: product
    actor: global-admin
    entities:
      - { entity: global-admin, effect: changes, facts: [Selected tenant] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard
---

# Switch tenant in the switcher

## Trigger

A global admin managing one tenant needs another.

## Outcome

The dashboard now manages the other tenant.
