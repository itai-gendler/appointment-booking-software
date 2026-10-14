---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member opens the calendar
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The Member has no access, so the Product cannot decrypt client details and asks for a grant"
    kind: condition
    entities:
      - { entity: member, effect: reads, facts: [Access] }
      - { entity: client, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Browse without access to client details

## Trigger

A staff member who was never granted access opens the calendar.

## Outcome

Appointments show without client details, with a note to get a team member to grant access.
