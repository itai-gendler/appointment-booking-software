---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Grant access for the colleague and confirms
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::staff
  - text: "The Product shares every client's key with the colleague's passkeys and records the Member's access"
    kind: product
    actor: staff-member
    entities:
      - { entity: member, effect: changes, facts: [Access] }
      - { entity: client, effect: reads, facts: [] }
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::staff
---

# Grant a colleague access to appointments

## Trigger

A colleague has joined and set up their passkey but can't see appointments.

## Outcome

The colleague can decrypt every client's details.
