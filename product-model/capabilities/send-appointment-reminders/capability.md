---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/(components)/EmailReminder.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/send-emails/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Send appointment reminders

When a staff member opens the dashboard home of a ready tenant, reminders go
out for confirmed appointments up to tomorrow evening, each reminder once.
