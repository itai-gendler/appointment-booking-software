---
appliesTo:
  - { type: entity, id: absence, effect: removes }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: agent }, { verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/utils.ts" }
---

# Every staff member of the tenant and global admins delete absences

Tenant admins, appointment managers and global admins all manage the absences of a tenant's agents.
