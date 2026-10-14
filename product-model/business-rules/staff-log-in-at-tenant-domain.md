---
appliesTo:
  - { type: capability, id: log-in }
  - { type: entity, id: tenant, facts: [Domain] }
references:
  - { kind: code, role: implementation, target: "src/routes/api/auth/login/+server.ts" }
---

# Staff members log in at their tenant's domain

A staff member's login works only at their own tenant's domain; global admins log in at any.
