---
appliesTo:
  - { type: capability, id: remove-member }
  - { type: entity, id: member, effect: removes }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/user-service.ts#UserService" }
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
---

# A tenant keeps at least one staff member with access

The last staff member who can read client details cannot be removed, and nobody removes themselves.
