---
entities:
  - { entity: appointment, shows: [Date and time, Name, E-mail address, Phone number] }
  - { entity: channel, shows: [Name] }
entryPoints:
  - web: /clients
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/clients/(components)/appointment-list.svelte" }
---

# My appointments

The client's upcoming appointments with this tenant, requested or confirmed.
