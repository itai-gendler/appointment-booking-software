---
kind: primary
routes:
  web: Web
steps:
  - text: "Housekeeping runs and finds appointments older than the Tenant's retention period"
    kind: condition
    unattended: true
    entities:
      - { entity: tenant, effect: reads, facts: [Appointment retention] }
      - { entity: appointment, effect: reads, facts: [Date and time] }
    contexts:
      web:
        place: web::dashboard::calendar
  - text: The Product deletes those Appointment records
    kind: product
    entities:
      - { entity: appointment, effect: removes, from: Confirmed }
    contexts:
      web:
        place: web::dashboard::calendar
---

# Delete appointments past retention

## Trigger

The twice-daily housekeeping runs.

## Outcome

Appointments older than the retention period are gone from the calendar.

## Edge cases

- Old requested appointments are deleted the same way.
