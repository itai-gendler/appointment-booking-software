---
entities:
  - { entity: passkey, collects: [Name] }
entryPoints:
  - web: /confirm/setup-passkey
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/confirm/setup-passkey/setup-passkey-form.svelte" }
---

# Passkey setup

Where a staff member who confirmed their e-mail address creates their first
passkey.
