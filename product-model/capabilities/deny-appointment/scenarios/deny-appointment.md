---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member opens the requested appointment, chooses Deny Appointment and confirms"
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product e-mails the rejection when the client wishes updates
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, E-mail address, Language, E-mail updates] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product deletes the requested Appointment
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: removes, from: Requested }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Deny a requested appointment

## Trigger

A request cannot be served.

## Outcome

The request is gone and its slot is free again; the client is told if they wished e-mails.
