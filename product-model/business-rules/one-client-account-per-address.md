---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: entity, id: client, effect: creates }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# A client has one account per tenant

An e-mail address has at most one client account at a tenant; a returning client logs in with their PIN instead of registering again.
