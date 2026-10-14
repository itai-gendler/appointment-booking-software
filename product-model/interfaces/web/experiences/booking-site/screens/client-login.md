---
entities:
  - { entity: client, collects: [E-mail address, PIN] }
entryPoints:
  - web: /clients/login
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/clients/login/client-login-form.svelte" }
---

# Client login

Where a client enters their e-mail address and PIN to see their appointments.
