---
entities:
  - { entity: account, shows: [Name, E-mail language], collects: [Name, E-mail language] }
entryPoints:
  - web: /dashboard/account/general
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/account/general/+page.svelte" }
---

# Account settings

The person's own name and e-mail language.
