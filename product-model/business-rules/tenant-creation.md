---
appliesTo:
  - { type: entity, id: tenant, effect: creates }
permits:
  - actors: [global-admin]
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/+server.ts" }
---

# Only global admins add tenants

Adding a tenant is reserved to the people who run the server.
