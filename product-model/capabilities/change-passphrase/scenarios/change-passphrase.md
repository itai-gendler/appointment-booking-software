---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin enters the current passphrase and the new one twice
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::dashboard::passphrase
  - text: The Product checks the current passphrase and saves the new one on the Account
    kind: product
    actor: global-admin
    entities:
      - { entity: account, effect: changes, facts: [Passphrase] }
    contexts:
      web:
        place: web::dashboard::passphrase
---

# Change the passphrase

## Trigger

A global admin wants a backup way to log in.

## Outcome

The account has the new passphrase.

## Edge cases

- A global admin without a passphrase sets one without giving a current one.
- A new passphrase shorter than 30 characters, or one repeated differently, is refused.
