---
domain: staff
relations:
  - { entity: notification, verb: receives, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/central-schema.ts#user" }
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
---

# Member

A staff member's place on one tenant's staff, as listed on the Staff page:
the role they hold there and whether they can read client details.

## Information kept

- **Role** — Tenant Admin, who manages agents, channels, absences, settings, staff and appointments, or Appointment Manager, who manages absences and appointments
- **Access** — whether they can decrypt client details: Granted, or Not granted, shown as "Can't see appointments"
