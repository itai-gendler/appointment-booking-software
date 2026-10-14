---
entities:
  - { entity: tenant, shows: [Website, Imprint, Privacy statement], collects: [Website, Imprint, Privacy statement] }
entryPoints:
  - web: /dashboard/settings/links
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/settings/(components)/edit-settings-form/edit-settings-form-links.svelte" }
---

# Links settings

The tenant's website and legal links.
