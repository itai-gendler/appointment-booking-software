---
domain: account
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/account/passkeys/(components)/add-passkey-form/add-passkey-form.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/auth/passkeys/+server.ts" }
---

# Add passkey

A person adds another passkey to their account, up to three. A staff member's
new passkey is given the same access to client details as their others.
