---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Move appointment
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The calendar shows the available slots of the appointment's channel"
    kind: condition
    entities:
      - { entity: appointment, effect: reads, facts: [] }
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Staff member picks a free slot and confirms the move
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product moves the Appointment to the slot and its agent
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: changes, facts: [Date and time] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product e-mails the update when the client wishes updates
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, E-mail address, Language, E-mail updates] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Move an appointment

## Trigger

A client asks for another time.

## Outcome

The appointment sits at the new time; the client is told if they wished e-mails.
