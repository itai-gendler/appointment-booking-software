---
availability:
  - { place: web::staff-sign-in }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/confirm/setup-passkey/setup-passkey-form.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/auth/register/[id]/+server.ts" }
---

# Set up passkey

After confirming their e-mail address, a staff member creates the passkey they
sign in with. The passkey must support the security extension that unlocks
their encryption keys.
