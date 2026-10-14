---
domain: account
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/api/auth/passkeys/[passkeyId]/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/account/passkeys/(components)/delete-passkey-form/delete-passkey-form.svelte" }
---

# Delete passkey

A person deletes one of their passkeys after typing its name. The last passkey
and the one used for the current session stay.
