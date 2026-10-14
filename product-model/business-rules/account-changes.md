---
appliesTo:
  - { type: entity, id: account, effect: changes, facts: [Name, E-mail address, E-mail language] }
permits:
  - related: [{ verb: uses, entity: staff-member }]
  - related: [{ verb: uses, entity: global-admin }]
  - actors: [global-admin]
  - related: [{ verb: uses, entity: staff-member }, { verb: holds, entity: member }, { verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
references:
  - { kind: code, role: implementation, target: "src/routes/api/me/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
---

# People change their own account; tenant admins change their staff's name and e-mail address

A person changes their own name and e-mail language. A tenant admin, or a
global admin managing the tenant, changes a staff member's name and e-mail
address from the staff page.
