---
domain: tenants
availability:
  - { place: web::administration }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/tenant-admin-service.ts#TenantAdminService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/tenants/(components)/delete-tenant-form/delete-tenant-form.svelte" }
---

# Delete tenant

A global admin deletes a tenant after typing its short name, with all its
staff, agents, channels, clients and appointments. The tenant currently
selected cannot be deleted.
