---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin starts the configuration of the new server
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::setup
  - text: The Global Admin enters their name and e-mail address and creates a passkey
    kind: actor
    actor: global-admin
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::setup
  - text: The Product creates the Account with that Passkey and e-mails a link to confirm the address
    kind: product
    actor: global-admin
    entities:
      - { entity: account, effect: creates, to: Invited, facts: [Name, E-mail address, E-mail language] }
      - { entity: passkey, effect: creates, facts: [Name, Created], with: account }
    contexts:
      web:
        place: web::staff-sign-in::setup
  - text: The page asks the Global Admin to check the e-mail sent to that address
    kind: condition
    entities:
      - { entity: account, effect: reads, facts: [E-mail address] }
      - { entity: global-admin, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::setup
---

# Create the admin account with a passkey

## Trigger

A person opens a new server for the first time and starts the configuration.

## Outcome

The first global admin's account exists, waiting for its e-mail address to be confirmed through the link just sent.

## Edge cases

- Resend E-Mail on that page sends the link again.
