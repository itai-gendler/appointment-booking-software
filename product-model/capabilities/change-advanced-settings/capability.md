---
domain: settings
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/(components)/edit-settings-form/edit-settings-form-advanced.svelte" }
---

# Change advanced settings

Compliance and required client data: after how long appointments are deleted,
and whether clients must give a phone number.
