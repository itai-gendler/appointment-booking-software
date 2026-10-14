---
kind: validation
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
  - text: "The domain is not their tenant's, so the Product refuses the login"
    kind: condition
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Log in at another tenant's domain

## Trigger

A staff member tries to log in at a domain that is not their tenant's.

## Outcome

They are not signed in; the login fails.
