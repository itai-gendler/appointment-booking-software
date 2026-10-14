---
entities:
  - { entity: account, collects: [E-mail address, Passphrase] }
entryPoints:
  - web: /login
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/login/+page.svelte" }
---

# Login

Where staff members and global admins log in with a passkey or, for a global
admin, a passphrase.
