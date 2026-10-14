---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member names the passkey, creates it and confirms with it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
  - text: The Product saves the Passkey and the encryption keys it unlocks
    kind: product
    actor: staff-member
    entities:
      - { entity: passkey, effect: creates, facts: [Name, Created] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
  - text: The Product grants the Member access because the tenant has no appointment yet
    kind: product
    entities:
      - { entity: member, effect: changes, facts: [Access] }
      - { entity: appointment, effect: reads, facts: [] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
  - text: The Product takes the Staff member to log in with the new passkey
    kind: product
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Set up a passkey before the tenant has appointments

## Trigger

A staff member sets up their passkey while their tenant has no appointment yet.

## Outcome

The passkey is saved and the staff member already has access to client details.
