---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses a free slot and searches the client by e-mail address
    kind: actor
    actor: staff-member
    entities:
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "Nobody is registered with that address, and the Staff member confirms registering the client"
    kind: actor
    actor: staff-member
    entities:
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Staff member adds the client's details and adds the appointment"
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Product creates the Client's account at this tenant"
    kind: product
    actor: staff-member
    entities:
      - { entity: client, effect: creates, facts: [E-mail address] }
      - { entity: account, effect: reads, facts: [] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product books the confirmed Appointment for the new client
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: creates, to: Confirmed, facts: [Date and time, Duration, Time zone, Name, E-mail address, Phone number, Language, E-mail updates, Progress, Booked at] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Add an appointment for a new client

## Trigger

Someone who never booked before calls for an appointment.

## Outcome

The new client and their confirmed appointment exist.

## Edge cases

- Creating a new client takes a bit longer, and the summary says so.
