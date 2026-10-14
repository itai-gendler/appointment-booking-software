---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin enters their e-mail address and passphrase
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::login
  - text: The Product checks the passphrase of the Account and signs the Global Admin in
    kind: product
    actor: global-admin
    entities:
      - { entity: account, effect: reads, facts: [E-mail address, Passphrase] }
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Log in with a passphrase

## Trigger

A global admin who set a passphrase chooses to use it.

## Outcome

The global admin is signed in.
