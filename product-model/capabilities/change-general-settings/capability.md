---
domain: settings
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/+server.ts" }
---

# Change general settings

The tenant's public name, description, logo, the languages clients see and the
default language.
