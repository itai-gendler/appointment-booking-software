---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/(components)/AppointmentProgress.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/progress/+server.ts" }
---

# Change appointment progress

On the day of a booked appointment, or after it, a staff member records how it
is going: Not here yet, Waiting, In Progress or Done.
