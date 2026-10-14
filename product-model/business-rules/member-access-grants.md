---
appliesTo:
  - { type: entity, id: member, effect: changes, facts: [Access], contexts: [{ place: web::dashboard }] }
permits:
  - related: [{ verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Role, is: Tenant Admin }
      - { entity: member, fact: Access, is: Granted }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/grant-access-form/grant-access-form.svelte" }
  - { kind: code, role: implementation, target: "src/lib/server/services/user-service.ts#UserService" }
---

# Only a tenant admin with access grants access to client details

A colleague's access to client details is granted by a tenant admin who has
that access themselves, because granting it means sharing keys only they can
open. A tenant's first member, and a member who sets up their passkey while the
tenant has no appointment yet, receive access without a grant.
