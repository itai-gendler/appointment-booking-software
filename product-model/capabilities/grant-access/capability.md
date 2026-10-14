---
domain: staff
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/grant-access-form/grant-access-form.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/tunnels/add-staff-key-shares/+server.ts" }
---

# Grant access

A tenant admin who can read client details lets a colleague read them too: the
colleague's device keys are given access to every client of the tenant.
