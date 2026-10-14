---
domain: staff
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/staff/[staffId]/resend-invite/+server.ts" }
---

# Resend invitation

A tenant admin sends another invitation e-mail to someone who has not joined yet.
