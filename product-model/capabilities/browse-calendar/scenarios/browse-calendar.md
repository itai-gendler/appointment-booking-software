---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member picks a day or week, the channels and which appointments to show"
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Product shows each Channel's slots and Appointment entries, decrypting client details on the device"
    kind: product
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Duration, Name, Progress] }
      - { entity: channel, effect: reads, facts: [Name, Color] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Staff member opens an appointment to see the client's details"
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [Name, E-mail address, Phone number, Language] }
      - { entity: agent, effect: reads, facts: [Name] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Browse the calendar

## Trigger

A staff member prepares the day.

## Outcome

They see the day's appointments with each client's details, and the slots still free.

## Edge cases

- Week views show either the whole week or workdays only.
