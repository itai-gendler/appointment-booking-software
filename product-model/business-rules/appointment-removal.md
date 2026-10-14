---
appliesTo:
  - { type: entity, id: appointment, effect: removes }
permits:
  - related: [{ verb: receives, entity: channel }, { verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
  - related: [{ verb: books, entity: client }]
  - unattended: true
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Staff members cancel and deny appointments; clients cancel their own

A tenant's staff members cancel or deny any of its appointments. A client
cancels only appointments they booked, proving their PIN. Housekeeping deletes
appointments past the tenant's retention period.
