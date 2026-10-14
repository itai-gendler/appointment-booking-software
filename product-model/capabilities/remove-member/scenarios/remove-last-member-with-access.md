---
kind: validation
routes:
  web: Web
steps:
  - text: The Staff member tries to remove a colleague
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::staff
  - text: "No other Member has access, or it is the Staff member's own, so the Product refuses"
    kind: condition
    entities:
      - { entity: member, effect: reads, facts: [Access] }
      - { entity: staff-member, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::staff
---

# Remove the last staff member with access

## Trigger

A tenant admin tries to remove the only staff member who can read client details, or themselves.

## Outcome

The staff member stays.
