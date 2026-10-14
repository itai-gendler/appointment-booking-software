---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member changes their name and e-mail language and saves
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::account-settings
  - text: The Product saves the Account
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: changes, facts: [Name, E-mail language] }
    contexts:
      web:
        place: web::dashboard::account-settings
---

# Change name and e-mail language

## Trigger

A staff member wants e-mails in another language.

## Outcome

The account carries the new name and e-mail language.
