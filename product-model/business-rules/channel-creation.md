---
appliesTo:
  - { type: entity, id: channel, effect: creates }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/utils.ts" }
---

# Only tenant admins and global admins add channels

Managing a tenant's channels belongs to its tenant admins and to global admins; appointment managers do not add them.
