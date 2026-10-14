---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member types the passkey's name to confirm and deletes it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::passkeys
  - text: The Product deletes the Passkey
    kind: product
    actor: staff-member
    entities:
      - { entity: passkey, effect: removes }
    contexts:
      web:
        place: web::dashboard::passkeys
---

# Delete a passkey

## Trigger

A staff member lost a device.

## Outcome

The passkey is gone and can no longer sign in.
