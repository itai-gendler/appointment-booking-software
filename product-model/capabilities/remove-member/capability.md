---
domain: staff
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/staff-service.ts#StaffService" }
  - { kind: code, role: implementation, target: "src/lib/server/services/user-service.ts#UserService" }
---

# Remove member

A tenant admin removes a staff member, or withdraws an invitation, after
typing their e-mail address. The removed person loses their account and
passkeys.
