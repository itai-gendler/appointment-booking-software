---
kind: primary
routes:
  web: Web
steps:
  - text: The Client chooses Cancel on an upcoming appointment and confirms
    kind: actor
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::client-area::my-appointments
  - text: "The Product proves the Client's PIN and deletes the Appointment"
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: removes, from: Confirmed }
    contexts:
      web:
        place: web::client-area::my-appointments
  - text: The Product adds a cancellation Notification for each staff member the channel notifies
    kind: product
    actor: client
    entities:
      - { entity: notification, effect: creates, facts: [Kind, Created] }
      - { entity: staff-member, effect: reads, facts: [] }
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::client-area::my-appointments
---

# Cancel my appointment

## Trigger

A client can no longer come.

## Outcome

The appointment is gone and the channel's notified staff see a cancellation notification.

## Edge cases

- A requested appointment is cancelled the same way.
- The client loses the spot and has to book the next free appointment.
