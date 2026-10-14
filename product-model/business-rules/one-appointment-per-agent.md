---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: capability, id: add-appointment }
  - { type: capability, id: move-appointment }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# An agent has one appointment at a time and none while absent

A new or moved appointment is refused when its agent already has an
overlapping appointment that is not rejected, or an absence covering it.
Bookings for one agent are checked one after another, so two people cannot take
the same slot.
