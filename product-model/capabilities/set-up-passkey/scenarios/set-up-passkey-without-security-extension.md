---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member creates a passkey with their authenticator
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
  - text: "The authenticator lacks the required security extension, so the Product refuses the passkey"
    kind: condition
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
---

# Use an authenticator without the security extension

## Trigger

A staff member creates a passkey with an authenticator that cannot unlock encryption keys.

## Outcome

No passkey is saved; the page asks for a modern authenticator.
