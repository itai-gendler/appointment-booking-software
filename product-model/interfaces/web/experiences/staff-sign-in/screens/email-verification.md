---
entities:
  - { entity: account, shows: [E-mail address] }
entryPoints:
  - web: "/confirm/{token}"
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/confirm/[token]/+page.svelte" }
---

# E-mail verification

Opened from the emailed link: the person claims their account by confirming
their e-mail address.
