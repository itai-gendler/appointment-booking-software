---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member types the invited address to confirm and removes the member
    kind: actor
    actor: staff-member
    entities:
      - { entity: member, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::staff
  - text: The Product deletes the invited Account and its Member
    kind: product
    actor: staff-member
    entities:
      - { entity: member, effect: removes }
      - { entity: account, effect: removes, from: Invited }
    contexts:
      web:
        place: web::dashboard::staff
---

# Withdraw an invitation

## Trigger

A tenant admin invited the wrong address.

## Outcome

The invitation no longer works and the person is gone from the staff list.
