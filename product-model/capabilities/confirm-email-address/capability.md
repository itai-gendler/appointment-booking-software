---
availability:
  - { place: web::staff-sign-in }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/confirm/[token]/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/user-service.ts#UserService" }
---

# Confirm e-mail address

A person claims their account by opening the link e-mailed to them, when the
server was set up or when they were invited to a tenant's staff. The link works
once and only for a few minutes.
