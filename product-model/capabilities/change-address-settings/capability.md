---
domain: settings
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/config/+server.ts" }
---

# Change address settings

The visitor address included in appointment information for clients. Saving
it or the advanced settings for the first time completes the settings step of a
new tenant's onboarding.
