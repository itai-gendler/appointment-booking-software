---
appliesTo:
  - { type: entity, id: agent, effect: changes }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/utils.ts" }
---

# Only tenant admins and global admins change agents

Managing a tenant's agents belongs to its tenant admins and to global admins; appointment managers do not change them.
