---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member edits the name, description, logo and languages and saves"
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::general-settings
  - text: The Product saves the Tenant
    kind: product
    actor: staff-member
    entities:
      - { entity: tenant, effect: changes, facts: [Name, Description, Logo, Languages, Default language] }
    contexts:
      web:
        place: web::dashboard::general-settings
---

# Change name, description and languages

## Trigger

A tenant admin reviews how the organization presents itself.

## Outcome

The home page and booking site show the new details in the chosen languages.
