---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin chooses Select on a tenant
    kind: actor
    actor: global-admin
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::administration::tenants
  - text: "The Product makes it the Global Admin's selected tenant"
    kind: product
    actor: global-admin
    entities:
      - { entity: global-admin, effect: changes, facts: [Selected tenant] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::administration::tenants
---

# Select a tenant from the list

## Trigger

A global admin wants to configure a tenant.

## Outcome

The dashboard shows that tenant's agents, channels, absences, staff and settings.
