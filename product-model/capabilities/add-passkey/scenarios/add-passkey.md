---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member names a new passkey, creates it and confirms with it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::passkeys
  - text: The Product saves the Passkey and gives it access to the client details the Staff member can read
    kind: product
    actor: staff-member
    entities:
      - { entity: passkey, effect: creates, facts: [Name, Created] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::passkeys
---

# Add a passkey

## Trigger

A staff member wants to sign in from another device.

## Outcome

The new passkey is listed and can open the same client details as the others.

## Edge cases

- If adding fails partway, the partly added passkey is deleted again.
