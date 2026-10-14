---
kind: primary
routes:
  web: Web
steps:
  - text: The Client chooses to book on the home page
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::home
  - text: "The Client selects an appointment type that requires confirmation, an agent and a free slot"
    kind: actor
    actor: client
    entities:
      - { entity: channel, effect: reads, facts: [Name, Requires confirmation] }
      - { entity: appointment, effect: reads, facts: [] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Client adds their details and chooses Login with their PIN
    kind: actor
    actor: client
    entities: []
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: "The Product proves the PIN on the Client's device"
    kind: product
    actor: client
    entities:
      - { entity: client, effect: reads, facts: [E-mail address, PIN] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Client reviews the summary and chooses Request appointment
    kind: actor
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Product records the requested Appointment
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: creates, to: Requested, facts: [Date and time, Duration, Time zone, Name, E-mail address, Phone number, Language, E-mail updates, Progress, Booked at] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Product adds a Notification for each staff member the channel notifies and e-mails them
    kind: product
    actor: client
    entities:
      - { entity: notification, effect: creates, facts: [Kind, Created] }
      - { entity: staff-member, effect: reads, facts: [] }
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The Product e-mails the request details when the Client asked to be notified
    kind: product
    actor: client
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, E-mail address, Language, E-mail updates] }
    contexts:
      web:
        place: web::booking-site::book-appointment
  - text: The page says the tenant will confirm or deny the request soon
    kind: condition
    entities:
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::booking-site::book-appointment
---

# Request an appointment as a returning client

## Trigger

A client who booked before chooses a channel that requires confirmation.

## Outcome

The appointment is requested and holds its slot; the channel's notified staff are told, and the client hears by e-mail once it is decided if they asked to be notified.
