---
kind: validation
routes:
  web: Web
steps:
  - text: The Staff member tries to delete a passkey
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::passkeys
  - text: "It is the last Passkey or the current session's, so the Product refuses"
    kind: condition
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::passkeys
---

# Delete the last or current passkey

## Trigger

A person tries to delete their only passkey, or the one they signed in with.

## Outcome

The passkey stays.
