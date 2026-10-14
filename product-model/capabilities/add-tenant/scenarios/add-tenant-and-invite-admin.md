---
kind: primary
routes:
  web: Web
steps:
  - text: "The Global Admin enters a short name and a domain, and the e-mail address of the tenant admin to invite"
    kind: actor
    actor: global-admin
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::administration::tenants
  - text: The Product adds the Tenant with English as its language and default settings
    kind: product
    actor: global-admin
    entities:
      - { entity: tenant, effect: creates, to: Awaiting settings, facts: [Short name, Domain, Languages, Default language, Appointment retention, Phone number required] }
    contexts:
      web:
        place: web::administration::tenants
  - text: "The Product invites the address as the Tenant's Tenant Admin and e-mails the invitation"
    kind: product
    actor: global-admin
    entities:
      - { entity: account, effect: creates, to: Invited, facts: [Name, E-mail address, E-mail language] }
      - { entity: member, effect: creates, facts: [Role, Access] }
      - { entity: tenant, effect: reads, facts: [Name] }
    contexts:
      web:
        place: web::administration::tenants
---

# Add a tenant and invite its admin

## Trigger

An organization wants to collect appointments on this server.

## Outcome

The tenant exists, waiting for its settings, and the invited person has an e-mail to join as its tenant admin.
