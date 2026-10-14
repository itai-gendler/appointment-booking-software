---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member enters the website, imprint and privacy statement addresses and saves"
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::links-settings
  - text: "The Product saves the Tenant's links"
    kind: product
    actor: staff-member
    entities:
      - { entity: tenant, effect: changes, facts: [Website, Imprint, Privacy statement] }
    contexts:
      web:
        place: web::dashboard::links-settings
---

# Change website and legal links

## Trigger

A tenant admin publishes the organization's legal pages.

## Outcome

The home page links the website, and the footer links the imprint and privacy statement.

## Edge cases

- An address that is not an http or https URL is refused.
