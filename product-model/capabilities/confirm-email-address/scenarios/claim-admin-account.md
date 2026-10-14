---
kind: primary
routes:
  web: Web
steps:
  - text: The Global Admin opens the link and chooses Claim account
    kind: actor
    actor: global-admin
    entities:
      - { entity: account, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The Product confirms the Account
    kind: product
    actor: global-admin
    entities:
      - { entity: account, effect: changes, from: Invited, to: Confirmed, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::email-verification
  - text: The Product sends the Global Admin to log in and add the first tenant
    kind: product
    actor: global-admin
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::staff-sign-in::login
---

# Claim the global admin account

## Trigger

The person who set up the server opens the link e-mailed to them.

## Outcome

The global admin's account is confirmed and the page leads them to log in and add the first tenant.
