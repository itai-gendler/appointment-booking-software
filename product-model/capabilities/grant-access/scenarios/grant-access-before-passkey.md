---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member chooses Grant access for the colleague
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::staff
  - text: "The colleague has no Passkey yet, so the Product cannot grant access"
    kind: condition
    entities:
      - { entity: passkey, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::staff
---

# Grant access before the colleague has a passkey

## Trigger

A tenant admin grants access to someone who has not accepted the invitation or added a passkey.

## Outcome

Nothing changes; the page says the person must accept the invitation and add their passkey first.
