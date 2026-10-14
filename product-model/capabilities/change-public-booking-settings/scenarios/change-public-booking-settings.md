---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member turns Public and Requires Confirmation on or off and saves
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::public-booking-settings
  - text: "The Product saves the Channel's public booking settings"
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Public, Requires confirmation] }
    contexts:
      web:
        place: web::dashboard::public-booking-settings
---

# Change public booking settings

## Trigger

A tenant admin opens a channel to the public and wants to vet each request.

## Outcome

The channel is offered on the booking site, and its new appointments wait for confirmation.
