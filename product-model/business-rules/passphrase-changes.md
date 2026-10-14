---
appliesTo:
  - { type: entity, id: account, effect: changes, facts: [Passphrase] }
permits:
  - related: [{ verb: uses, entity: global-admin }]
references:
  - { kind: code, role: implementation, target: "src/routes/api/me/passphrase/+server.ts" }
---

# Only a global admin sets their own passphrase

Passphrases are a backup way for global admins to log in; staff members sign in with passkeys only. A passphrase has at least 30 characters.
