---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member opens the requested appointment and chooses Confirm Appointment
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product confirms the Appointment
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: changes, from: Requested, to: Confirmed, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product adds a Notification for each staff member the channel notifies
    kind: product
    actor: staff-member
    entities:
      - { entity: notification, effect: creates, facts: [Kind, Created] }
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product e-mails the booking details when the client wishes updates
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, E-mail address, Language, E-mail updates] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Confirm a requested appointment

## Trigger

A request waits in a channel that requires confirmation.

## Outcome

The appointment is booked; the client knows if they wished e-mails.
