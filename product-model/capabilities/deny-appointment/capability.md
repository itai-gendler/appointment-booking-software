---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/(components)/Appointment.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/[appointmentId]/deny/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Deny appointment

A staff member denies a requested appointment. The request is deleted and its
slot freed, and the client is e-mailed if they wish updates.
