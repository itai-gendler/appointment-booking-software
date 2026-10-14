---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: The Global Admin enters their name and e-mail address and creates a passkey
    kind: actor
    actor: global-admin
    capability: create-admin-account
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::setup
  - text: The Product creates the Account and e-mails a link to confirm the address
    kind: product
    actor: global-admin
    capability: create-admin-account
    entities:
      - { entity: account, effect: creates, to: Invited, facts: [Name, E-mail address, E-mail language] }
      - { entity: passkey, effect: creates, facts: [Name, Created], with: account }
    contexts:
      web:
        place: web::staff-sign-in::setup
  - text: The Global Admin opens the emailed link and claims the account
    kind: actor
    actor: global-admin
    capability: confirm-email-address
    entities:
      - { entity: account, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The Product confirms the Account and sends the Global Admin to log in
    kind: product
    actor: global-admin
    capability: confirm-email-address
    entities:
      - { entity: account, effect: changes, from: Invited, to: Confirmed, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: "The Global Admin logs in, confirming with their authenticator"
    kind: actor
    actor: global-admin
    capability: log-in
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::login
  - text: The Product signs the Global Admin in
    kind: product
    actor: global-admin
    capability: log-in
    entities:
      - { entity: passkey, effect: changes, facts: [Last used] }
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Set up a new server

## Trigger

A person installs OpenReception and opens it for the first time.

## Outcome

The global admin's account is confirmed and they are logged in, ready to add the first tenant.
