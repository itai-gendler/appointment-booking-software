---
appliesTo:
  - { type: entity, id: account, effect: removes }
permits:
  - actors: [global-admin]
  - related: [{ verb: uses, entity: staff-member }, { verb: holds, entity: member }, { verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
---

# Only tenant admins and global admins remove a staff member's account

Removing a staff member, or withdrawing their invitation, deletes their account; it belongs to the tenant's tenant admins and to global admins.
