---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member opens the link from the invitation and claims the account
    kind: actor
    actor: staff-member
    entities:
      - { entity: account, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The Product confirms the Account
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: changes, from: Invited, to: Confirmed, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The Product marks the Tenant ready
    kind: product
    actor: staff-member
    entities:
      - { entity: tenant, effect: changes, from: Awaiting staff, to: Ready, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
---

# Confirm the member a tenant was waiting for

## Trigger

A tenant has a complete channel but no staff yet, and an invited person confirms their address.

## Outcome

The account is confirmed and the tenant is ready: its booking site starts offering appointments.
