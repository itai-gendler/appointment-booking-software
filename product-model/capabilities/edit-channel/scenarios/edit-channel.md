---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member edits the channel's name and description and saves"
    kind: actor
    actor: staff-member
    entities:
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::channel
  - text: The Product saves the Channel
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Name, Description] }
    contexts:
      web:
        place: web::dashboard::channel
---

# Edit name and description

## Trigger

A channel's wording no longer helps clients choose.

## Outcome

Clients see the new name and description.
