---
availability:
  - { place: web::staff-sign-in }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/confirm/resend/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/auth/resend-confirmation/+server.ts" }
---

# Resend verification e-mail

A person whose confirmation link was wrong or outdated asks for a new one.
