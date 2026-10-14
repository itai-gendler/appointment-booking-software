---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member enters the visitor address and saves
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::address-settings
  - text: The Product saves the address and moves the Tenant on to its agents step
    kind: product
    actor: staff-member
    entities:
      - { entity: tenant, effect: changes, from: Awaiting settings, to: Awaiting agents, facts: [Visitor address] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::address-settings
---

# Save the settings of a new tenant

## Trigger

A tenant admin follows the onboarding guide of a new tenant and saves its address.

## Outcome

The settings step is done; the guide moves on to agents.
