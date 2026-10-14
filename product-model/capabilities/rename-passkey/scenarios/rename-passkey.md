---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member enters a new name for the passkey
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::passkeys
  - text: The Product renames the Passkey
    kind: product
    actor: staff-member
    entities:
      - { entity: passkey, effect: changes, facts: [Name] }
    contexts:
      web:
        place: web::dashboard::passkeys
---

# Rename a passkey

## Trigger

A staff member cannot tell their passkeys apart.

## Outcome

The passkey carries the new name.
