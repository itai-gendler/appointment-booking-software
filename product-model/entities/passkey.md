---
domain: account
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/central-schema.ts#userPasskey" }
---

# Passkey

A passkey a person signs in with. It also unlocks the keys that let a staff
member decrypt client details.

## Information kept

- **Name** — a name the person recognizes it by
- **Created** — when it was added
- **Last used** — when it was last used to sign in
