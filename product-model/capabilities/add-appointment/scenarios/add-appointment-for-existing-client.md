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
  - text: "The Product finds the Client's account at this tenant"
    kind: product
    actor: staff-member
    entities:
      - { entity: client, effect: reads, facts: [E-mail address] }
      - { entity: account, effect: reads, facts: [] }
      - { entity: tenant, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Staff member picks the agent if several are free, adds the client's details and adds the appointment"
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
      - { entity: client, effect: reads, facts: [] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Product books the confirmed Appointment, encrypted for the client and every staff member with access"
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: creates, to: Confirmed, facts: [Date and time, Duration, Time zone, Name, E-mail address, Phone number, Language, E-mail updates, Progress, Booked at] }
      - { entity: client, effect: reads, facts: [] }
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

# Add an appointment for an existing client

## Trigger

A client calls to book.

## Outcome

The appointment is confirmed in the calendar; the client gets an e-mail if they wish updates.
