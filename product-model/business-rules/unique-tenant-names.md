---
appliesTo:
  - { type: capability, id: add-tenant }
  - { type: capability, id: edit-tenant }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/tenant-admin-service.ts#TenantAdminService" }
---

# A tenant's short name and domain are unique on the server

No two tenants share a short name or a domain; the short name is fixed once the tenant is added.
