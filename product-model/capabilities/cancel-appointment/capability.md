---
availability:
  - { place: web::dashboard }
  - { place: web::client-area }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/(components)/Appointment.svelte" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/clients/(components)/appointment-list.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/[appointmentId]/delete/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/[appointmentId]/delete-by-client/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Cancel appointment

An appointment is cancelled and deleted, freeing its slot. Staff cancel from the
calendar and the client is e-mailed if they wish updates; a client cancels their
own from their appointments and the channel's notified staff are told.
