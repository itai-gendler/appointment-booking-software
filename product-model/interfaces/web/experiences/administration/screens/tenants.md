---
entities:
  - { entity: tenant, shows: [Short name, Domain], collects: [Short name, Domain] }
  - { entity: account, collects: [E-mail address] }
entryPoints:
  - web: /dashboard/tenants
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/tenants/+page.svelte" }
---

# Tenants

All tenants on the server, where global admins add, edit, select and delete
them.
