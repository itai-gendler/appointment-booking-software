---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses a free slot and marks that the client has no e-mail
    kind: actor
    actor: staff-member
    entities:
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Staff member adds the client's name and phone number and adds the appointment"
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product registers the Client without an address
    kind: product
    actor: staff-member
    entities:
      - { entity: client, effect: creates, facts: [E-mail address] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product books the confirmed Appointment
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: creates, to: Confirmed, facts: [Date and time, Duration, Time zone, Name, E-mail address, Phone number, Language, E-mail updates, Progress, Booked at] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Add an appointment for a client without e-mail

## Trigger

A client without an e-mail address books by phone.

## Outcome

The confirmed appointment exists; no e-mail is ever sent for it.
