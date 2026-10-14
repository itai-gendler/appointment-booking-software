---
appliesTo:
  - { type: entity, id: passkey, effect: removes }
permits:
  - related: [{ verb: has, entity: account }, { verb: uses, entity: staff-member }]
  - related: [{ verb: has, entity: account }, { verb: uses, entity: global-admin }]
references:
  - { kind: code, role: implementation, target: "src/routes/api/auth/passkeys/[passkeyId]/+server.ts" }
---

# People delete only their own passkeys

A passkey is managed by the person whose account it belongs to.
