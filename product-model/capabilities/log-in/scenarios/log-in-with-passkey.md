---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member enters their e-mail address and confirms with their authenticator
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::login
  - text: The Product recognizes the Account and its Passkey and signs the Staff member in
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: reads, facts: [E-mail address] }
      - { entity: passkey, effect: changes, facts: [Last used] }
    contexts:
      web:
        place: web::staff-sign-in::login
  - text: The Product opens the dashboard
    kind: product
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Log in with a passkey

## Trigger

A staff member opens the login page of their tenant.

## Outcome

They are signed in and the dashboard opens.
