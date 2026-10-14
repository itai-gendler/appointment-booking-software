---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/(components)/MoveAppointment.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/[appointmentId]/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Move appointment

A staff member moves an appointment to another free slot of its channel,
possibly with another agent; the client is e-mailed if they wish updates.
