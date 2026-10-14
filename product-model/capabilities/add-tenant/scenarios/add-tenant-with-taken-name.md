---
kind: validation
routes:
  web: Web
steps:
  - text: The Global Admin enters a short name and a domain
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::administration::tenants
  - text: "Another Tenant already has that short name or domain, so the Product refuses"
    kind: condition
    entities:
      - { entity: tenant, effect: reads, facts: [Short name, Domain] }
    contexts:
      web:
        place: web::administration::tenants
---

# Add a tenant with a name or domain in use

## Trigger

A global admin picks a short name or domain another tenant has, or invites an address already in use.

## Outcome

No tenant is added; the page says what is taken.
