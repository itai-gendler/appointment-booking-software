---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member types the colleague's e-mail address to confirm and removes them"
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::staff
  - text: "The Product deletes the colleague's Member, Account and Passkey list"
    kind: product
    actor: staff-member
    entities:
      - { entity: member, effect: removes }
      - { entity: account, effect: removes, from: Confirmed }
      - { entity: passkey, effect: removes, with: account }
    contexts:
      web:
        place: web::dashboard::staff
---

# Remove a staff member

## Trigger

A colleague leaves the organization.

## Outcome

The colleague is gone from the staff list and can no longer log in or read client details.
