---
appliesTo:
  - { type: entity, id: tenant, effect: removes }
permits:
  - actors: [global-admin]
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/+server.ts" }
---

# Only global admins delete tenants

Deleting a tenant, with everything it keeps, is reserved to global admins.
