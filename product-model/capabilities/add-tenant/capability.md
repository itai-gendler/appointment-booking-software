---
domain: tenants
availability:
  - { place: web::administration }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/tenants/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/tenant-admin-service.ts#TenantAdminService" }
---

# Add tenant

A global admin adds a tenant with a unique short name and domain, and may
invite its first tenant admin by e-mail.
