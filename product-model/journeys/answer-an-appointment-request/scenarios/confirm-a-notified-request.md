---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: The Staff member opens the new request notification
    kind: actor
    actor: staff-member
    capability: open-notification
    entities:
      - { entity: notification, effect: reads, facts: [Kind] }
    contexts:
      web:
        place: web::dashboard::notifications
  - text: The Product opens the calendar on the Appointment with its details
    kind: product
    actor: staff-member
    capability: open-notification
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Staff member chooses Confirm Appointment
    kind: actor
    actor: staff-member
    capability: confirm-appointment
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Product confirms the Appointment and notifies the channel's staff"
    kind: product
    actor: staff-member
    capability: confirm-appointment
    entities:
      - { entity: appointment, effect: changes, from: Requested, to: Confirmed, facts: [] }
      - { entity: notification, effect: creates, facts: [Kind, Created] }
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Confirm a request from its notification

## Trigger

A client requests an appointment in a channel that notifies the staff member.

## Outcome

The appointment is confirmed and the channel's notified staff are told.
