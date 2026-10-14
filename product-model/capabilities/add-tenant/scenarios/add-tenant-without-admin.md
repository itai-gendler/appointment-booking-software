---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin enters a short name and a domain and leaves the invitation off
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::administration::tenants
  - text: The Product adds the Tenant with English as its language and default settings
    kind: product
    actor: global-admin
    entities:
      - { entity: tenant, effect: creates, to: Awaiting settings, facts: [Short name, Domain, Languages, Default language, Appointment retention, Phone number required] }
    contexts:
      web:
        place: web::administration::tenants
---

# Add a tenant without inviting anyone

## Trigger

A global admin will set up a tenant themselves.

## Outcome

The tenant exists, waiting for its settings.
