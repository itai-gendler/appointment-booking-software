---
entities:
  - { entity: tenant, shows: [Visitor address], collects: [Visitor address] }
entryPoints:
  - web: /dashboard/settings/address
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/(components)/edit-settings-form/edit-settings-form-address.svelte" }
---

# Address settings

The tenant's visitor address.
