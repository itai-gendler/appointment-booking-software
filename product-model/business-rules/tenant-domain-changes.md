---
appliesTo:
  - { type: entity, id: tenant, effect: changes, facts: [Domain] }
permits:
  - actors: [global-admin]
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
---

# Only global admins change a tenant's domain

A tenant's domain is set by global admins; its short name never changes.
