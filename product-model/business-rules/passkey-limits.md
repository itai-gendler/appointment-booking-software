---
appliesTo:
  - { type: capability, id: add-passkey }
  - { type: capability, id: delete-passkey }
references:
  - { kind: code, role: implementation, target: "src/routes/api/auth/passkeys/[passkeyId]/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/account/passkeys/+page.svelte" }
---

# An account keeps one to three passkeys

A person adds up to three passkeys. The last passkey, and the one the current session was opened with, cannot be deleted.
