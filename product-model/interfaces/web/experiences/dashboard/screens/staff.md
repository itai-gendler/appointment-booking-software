---
entities:
  - { entity: account, shows: [Name, E-mail address], collects: [Name, E-mail address, E-mail language] }
  - { entity: member, shows: [Role, Access], collects: [Role] }
entryPoints:
  - web: /dashboard/staff
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/+page.svelte" }
---

# Staff

The tenant's staff members with their role and whether they can see
appointments.
