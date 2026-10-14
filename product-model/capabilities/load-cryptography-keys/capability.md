---
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/(components)/MissingStaffCrypto.svelte" }
  - { kind: code, role: implementation, target: "src/lib/stores/staff-crypto.ts" }
---

# Load cryptography keys

A dashboard tab opened without the keys needed to read client details asks the
staff member to load them with their passkey. Settings can still be changed
without them.
