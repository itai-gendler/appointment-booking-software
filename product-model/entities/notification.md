---
domain: notifications
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/tenant-schema.ts#notification" }
  - { kind: code, role: implementation, target: "src/lib/server/services/notification-service.ts#NotificationService" }
---

# Notification

A dashboard notification telling a staff member about one of their channels'
appointments.

## Information kept

- **Kind** — New appointment request, Appointment confirmed, or Appointment cancelled
- **Created** — when it was created
