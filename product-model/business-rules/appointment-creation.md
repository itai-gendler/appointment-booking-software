---
appliesTo:
  - { type: entity, id: appointment, effect: creates }
permits:
  - actors: [client]
  - related: [{ verb: receives, entity: channel }, { verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
references:
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/staff-create/+server.ts" }
---

# Clients book and staff members add appointments

Anyone may book on a ready tenant's booking site; inside the dashboard, appointments are added by the tenant's staff members.
