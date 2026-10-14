---
appliesTo:
  - { type: entity, id: member, effect: creates }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/api/auth/invite/+server.ts" }
---

# Only tenant admins and global admins invite staff

Inviting someone to a tenant's staff belongs to its tenant admins and to global admins.
