---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: The Staff member opens the link from the invitation and claims the account
    kind: actor
    actor: staff-member
    capability: confirm-email-address
    entities:
      - { entity: account, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The Product confirms the Account and offers Setup Passkey
    kind: product
    actor: staff-member
    capability: confirm-email-address
    entities:
      - { entity: account, effect: changes, from: Invited, to: Confirmed, facts: [] }
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: "The Staff member names a passkey, creates it and confirms with it"
    kind: actor
    actor: staff-member
    capability: set-up-passkey
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
  - text: The Product saves the Passkey and takes the Staff member to log in
    kind: product
    actor: staff-member
    capability: set-up-passkey
    entities:
      - { entity: passkey, effect: creates, facts: [Name, Created] }
    contexts:
      web:
        place: web::staff-sign-in::passkey-setup
  - text: "The Staff member logs in, confirming with their authenticator"
    kind: actor
    actor: staff-member
    capability: log-in
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::login
  - text: The Product signs the Staff member in
    kind: product
    actor: staff-member
    capability: log-in
    entities:
      - { entity: passkey, effect: changes, facts: [Last used] }
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Accept an invitation

## Trigger

A person receives an invitation e-mail to a tenant's staff.

## Outcome

Their account is confirmed, their passkey is set up and they are logged in.
