---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member picks the agent, Recurring, a reason, the first and last day, weekdays and a time window, and adds it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::absences
  - text: The Product adds the recurring Absence for the Agent
    kind: product
    actor: staff-member
    entities:
      - { entity: absence, effect: creates, facts: [Kind, Reason, Start, End, Weekdays, Time window] }
      - { entity: agent, effect: reads, facts: [Name] }
    contexts:
      web:
        place: web::dashboard::absences
---

# Add a recurring absence

## Trigger

An agent is never available on Friday afternoons.

## Outcome

No slots are offered for the agent in that window on those weekdays, between the first and last day.

## Edge cases

- No weekday selected, or a from time after the to time, is refused.
