---
appliesTo:
  - { type: entity, id: account, effect: changes, to: Confirmed }
permits:
  - related: [{ verb: uses, entity: staff-member }]
  - related: [{ verb: uses, entity: global-admin }]
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/user-service.ts#UserService" }
---

# People confirm only their own account

An account is confirmed by the person it belongs to, through the link e-mailed to them.
