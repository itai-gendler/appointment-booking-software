---
kind: primary
routes:
  web: Web
steps:
  - text: "The Global Admin types the tenant's short name to confirm and deletes it"
    kind: actor
    actor: global-admin
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::administration::tenants
  - text: "The Product deletes the Tenant with its members, agents, channels and clients"
    kind: product
    actor: global-admin
    entities:
      - { entity: tenant, effect: removes, from: Ready }
      - { entity: member, effect: removes, with: tenant }
      - { entity: agent, effect: removes, with: tenant }
      - { entity: channel, effect: removes, from: Active, with: tenant }
      - { entity: client, effect: removes, with: tenant }
    contexts:
      web:
        place: web::administration::tenants
---

# Delete a tenant

## Trigger

An organization stops using the server.

## Outcome

The tenant and everything it kept are gone.

## Edge cases

- A tenant still being set up is deleted the same way.
