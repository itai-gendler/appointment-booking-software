---
kind: validation
routes:
  web: Web
steps:
  - text: The Global Admin enters a wrong current passphrase and a new one
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::dashboard::passphrase
  - text: "The current passphrase does not match the Account's, so the Product refuses"
    kind: condition
    entities:
      - { entity: account, effect: reads, facts: [Passphrase] }
    contexts:
      web:
        place: web::dashboard::passphrase
---

# Give a wrong current passphrase

## Trigger

A global admin mistypes their current passphrase.

## Outcome

The passphrase stays unchanged; the page says the current passphrase is incorrect.
