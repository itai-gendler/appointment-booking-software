---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member adds, changes or removes slot templates and saves"
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::channel-schedule
  - text: "The Product saves the Channel's schedule and rebuilds its slots"
    kind: product
    actor: staff-member
    entities:
      - { entity: channel, effect: changes, facts: [Schedule] }
    contexts:
      web:
        place: web::dashboard::channel-schedule
---

# Edit the schedule

## Trigger

Opening hours change.

## Outcome

Clients are offered slots by the new schedule; appointments already booked stay.
