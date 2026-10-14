---
appliesTo:
  - { type: entity, id: passkey, effect: changes }
permits:
  - related: [{ verb: has, entity: account }, { verb: uses, entity: staff-member }]
  - related: [{ verb: has, entity: account }, { verb: uses, entity: global-admin }]
references:
  - { kind: code, role: implementation, target: "src/routes/api/auth/passkeys/[passkeyId]/+server.ts" }
---

# People rename only their own passkeys

A passkey is managed by the person whose account it belongs to.
