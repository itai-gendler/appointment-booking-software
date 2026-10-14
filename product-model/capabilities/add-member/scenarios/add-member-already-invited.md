---
kind: validation
routes:
  web: Web
steps:
  - text: The Staff member enters an e-mail address and adds the member
    kind: actor
    actor: staff-member
    entities:
      - { entity: member, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::staff
  - text: "An Account already uses the address or has a pending invitation, so the Product refuses"
    kind: condition
    entities:
      - { entity: account, effect: reads, facts: [E-mail address] }
    contexts:
      web:
        place: web::dashboard::staff
---

# Invite someone already invited or registered

## Trigger

A tenant admin invites an address with a pending invitation or an existing account.

## Outcome

No second invitation is created; the page says the member could not be added.
