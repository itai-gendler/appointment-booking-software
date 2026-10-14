---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: capability, id: add-appointment }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# New clients book only while a staff member has access

A client account is created only while at least one staff member of the tenant can read client details, so every new client's details stay readable by the tenant.
