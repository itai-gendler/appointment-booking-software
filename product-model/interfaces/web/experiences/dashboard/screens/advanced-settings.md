---
entities:
  - { entity: tenant, shows: [Appointment retention, Phone number required], collects: [Appointment retention, Phone number required] }
entryPoints:
  - web: /dashboard/settings/advanced
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/(components)/edit-settings-form/edit-settings-form-advanced.svelte" }
---

# Advanced settings

Compliance and required client data: appointment retention and the phone
number requirement.
