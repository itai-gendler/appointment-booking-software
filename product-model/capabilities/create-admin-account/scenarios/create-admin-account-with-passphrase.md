---
kind: primary
routes:
  web: Web
steps:
  - text: "The Global Admin enters their name, e-mail address and a passphrase of at least 30 characters"
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::setup
  - text: The Product creates the Account with that passphrase and e-mails a link to confirm the address
    kind: product
    actor: global-admin
    entities:
      - { entity: account, effect: creates, to: Invited, facts: [Name, E-mail address, E-mail language, Passphrase] }
    contexts:
      web:
        place: web::staff-sign-in::setup
---

# Create the admin account with a passphrase

## Trigger

A person sets up a new server and prefers a passphrase to a passkey.

## Outcome

The first global admin's account exists with a passphrase, waiting for its e-mail address to be confirmed.

## Edge cases

- A passphrase shorter than 30 characters is refused.
- Giving both a passphrase and a passkey, or neither, is refused.
