---
kind: validation
routes:
  web: Web
steps:
  - text: The Global Admin submits the setup form
    kind: actor
    actor: global-admin
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::setup
  - text: "A global admin already exists, so the Product refuses to create another one"
    kind: condition
    entities:
      - { entity: global-admin, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::setup
---

# Refuse a second setup

## Trigger

Someone opens the setup of a server that already has a global admin.

## Outcome

No account is created; the server's home page no longer leads to the setup.
