---
appliesTo:
  - { type: capability, id: confirm-email-address }
  - { type: capability, id: resend-verification-email }
  - { type: capability, id: resend-invitation }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/invite-service.ts#InviteService" }
  - { kind: code, role: implementation, target: "src/lib/server/services/user-service.ts#UserService" }
---

# Confirmation links work once and briefly

A link to confirm an e-mail address works once and expires after ten minutes; a new one can be requested.
