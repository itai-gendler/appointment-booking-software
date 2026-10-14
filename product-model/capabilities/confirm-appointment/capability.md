---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/(components)/Appointment.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/[appointmentId]/confirm/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Confirm appointment

A staff member confirms a requested appointment. The channel's notified staff
are told, and the client is e-mailed if they wish updates.
