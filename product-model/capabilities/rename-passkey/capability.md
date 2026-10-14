---
domain: account
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/api/auth/passkeys/[passkeyId]/+server.ts" }
---

# Rename passkey

A person renames one of their passkeys to something they recognize.
