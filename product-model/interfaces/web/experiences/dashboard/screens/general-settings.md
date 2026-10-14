---
entities:
  - { entity: tenant, shows: [Name, Description, Logo, Languages, Default language], collects: [Name, Description, Logo, Languages, Default language] }
entryPoints:
  - web: /dashboard/settings/general
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/(components)/edit-settings-form/edit-settings-form-general.svelte" }
---

# General settings

The tenant's name, description, logo and languages.
