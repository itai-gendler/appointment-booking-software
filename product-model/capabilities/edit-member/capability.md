---
domain: staff
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/staff/[staffId]/+server.ts" }
---

# Edit member

A tenant admin changes a staff member's name, e-mail address and role.
