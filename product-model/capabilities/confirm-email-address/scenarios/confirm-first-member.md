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
  - text: "The Product grants access to the tenant's first Member"
    kind: product
    entities:
      - { entity: member, effect: changes, facts: [Access] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The page offers Setup Passkey as the next step
    kind: condition
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
---

# Confirm the tenant's first member

## Trigger

The first person invited to a tenant, usually its tenant admin, opens their invitation link.

## Outcome

The account is confirmed and, as the tenant's first member, already has access to client details.
