---
entities:
  - { entity: account, collects: [Name, E-mail address, Passphrase] }
  - { entity: passkey, collects: [Name] }
entryPoints:
  - web: /setup
  - web: /setup/create-admin-account
  - web: /setup/check-email
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/setup/create-admin-account/+page.server.ts" }
---

# Server setup

The first-run setup of a new server: creating the first global admin's account
and checking the e-mail sent to confirm it.
