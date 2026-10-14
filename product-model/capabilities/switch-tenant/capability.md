---
domain: tenants
availability:
  - { place: web::administration }
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/api/admin/tenant/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/components/layouts/sidebar-layout/components/tenant-switcher.svelte" }
---

# Switch tenant

A global admin selects the tenant they manage in the dashboard, from the
tenant list or the tenant switcher.
