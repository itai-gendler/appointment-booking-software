---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/(components)/add-appointment/AddAppointment.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/staff-create/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Add appointment

A staff member adds an appointment in a free slot of the calendar for an
existing client, a new client, or a client without e-mail. Appointments staff
add are confirmed at once.
