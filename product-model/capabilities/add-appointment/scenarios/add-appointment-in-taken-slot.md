---
kind: edge
routes:
  web: Web
steps:
  - text: The Staff member adds the appointment
    kind: actor
    actor: staff-member
    entities:
      - { entity: appointment, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: "The agent already has an Appointment or Absence then, so the Product refuses"
    kind: condition
    entities:
      - { entity: appointment, effect: reads, facts: [Date and time, Duration] }
      - { entity: absence, effect: reads, facts: [Start, End] }
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Add an appointment in a slot just taken

## Trigger

Another booking takes the slot while a staff member is adding an appointment.

## Outcome

Nothing is booked; the page says the agent is no longer available and offers to look for another appointment.
