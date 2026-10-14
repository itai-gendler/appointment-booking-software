---
appliesTo:
  - { type: entity, id: member, effect: changes, facts: [Role] }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/staff/[staffId]/+server.ts" }
---

# Only tenant admins and global admins change a staff member's role

Roles are Tenant Admin and Appointment Manager; nobody is made a global admin from a tenant's staff page.
