---
kind: validation
routes:
  web: Web
steps:
  - text: The Staff member opens Add Passkey
    kind: actor
    actor: staff-member
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::passkeys
  - text: "Three passkeys exist already, so the Product says the maximum is reached"
    kind: condition
    entities:
      - { entity: passkey, effect: reads, facts: [Name] }
    contexts:
      web:
        place: web::dashboard::passkeys
---

# Add a fourth passkey

## Trigger

A person who already has three passkeys tries to add one more.

## Outcome

No passkey is added; the page says the maximum is reached.
