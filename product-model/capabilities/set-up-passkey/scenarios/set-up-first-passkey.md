---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member names the passkey and creates it with their authenticator
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
  - text: The Staff member confirms with the new passkey to enable encryption
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
  - text: The Product takes the Staff member to log in with the new passkey
    kind: product
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Set up the first passkey

## Trigger

A staff member confirmed their e-mail address and chose Setup Passkey.

## Outcome

The passkey is saved together with the staff member's encryption keys, and they are taken to log in with it.
