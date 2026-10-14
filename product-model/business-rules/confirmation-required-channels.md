---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: capability, id: add-appointment }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Bookings in a channel that requires confirmation start as requests

An appointment a client books in a channel that requires confirmation is
requested until staff confirm or deny it; elsewhere it is confirmed at once.
Appointments staff add are always confirmed.
