---
domain: staff
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
  - { kind: code, role: implementation, target: "src/routes/api/auth/invite/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/invite-service.ts#InviteService" }
---

# Add member

A tenant admin invites a person to the tenant's staff as Tenant Admin or
Appointment Manager. The invitation e-mail is written in the language chosen.
