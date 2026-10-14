---
appliesTo:
  - { type: entity, id: global-admin, effect: changes, facts: [Selected tenant] }
permits:
  - self: true
references:
  - { kind: code, role: implementation, target: "src/routes/api/admin/tenant/+server.ts" }
---

# Only global admins select the tenant they manage

Staff members always work in their own tenant; global admins choose which tenant the dashboard manages.
