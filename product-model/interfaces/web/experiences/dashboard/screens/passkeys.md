---
entities:
  - { entity: passkey, shows: [Name, Created, Last used], collects: [Name] }
entryPoints:
  - web: /dashboard/account/passkeys
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/account/passkeys/+page.svelte" }
---

# Passkeys

The person's passkeys, marking the one used for the current session.
