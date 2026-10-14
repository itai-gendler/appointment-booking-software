---
appliesTo:
  - { type: entity, id: member, effect: removes }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
---

# Only tenant admins and global admins remove staff

Removing a staff member, or withdrawing an invitation, belongs to the tenant's tenant admins and to global admins.
