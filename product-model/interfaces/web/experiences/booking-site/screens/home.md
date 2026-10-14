---
entities:
  - { entity: tenant, shows: [Name, Description, Logo, Website, Imprint, Privacy statement] }
entryPoints:
  - web: /
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/+page.svelte" }
---

# Home page

The tenant's public home page: who the tenant is, and the way into booking.
When the tenant is not ready, it says it is not ready to accept appointments.
