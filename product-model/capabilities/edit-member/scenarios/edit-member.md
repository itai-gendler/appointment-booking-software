---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member changes the colleague's name, e-mail address or role and saves"
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::staff
  - text: "The Product saves the colleague's Account and Member"
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: changes, facts: [Name, E-mail address] }
      - { entity: member, effect: changes, facts: [Role] }
    contexts:
      web:
        place: web::dashboard::staff
---

# Edit a staff member

## Trigger

A colleague becomes the tenant's admin.

## Outcome

The colleague's name, address and role are updated.

## Edge cases

- Only Tenant Admin and Appointment Manager can be chosen; nobody is made a global admin here.
