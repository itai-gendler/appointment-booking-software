---
appliesTo:
  - { type: entity, id: tenant, effect: changes }
permits:
  - actors: [global-admin]
  - related: [{ verb: has, entity: member }, { verb: holds, entity: staff-member }]
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/tenant-admin-service.ts#TenantAdminService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/+page.svelte" }
---

# A tenant's setup moves on as it is completed

A new tenant waits for its settings, then its first agent, then a complete
channel — active, with an agent and a schedule — and then its first staff
member, and is ready once all exist. Saving the address or advanced settings
completes the settings step. Removing the last agent or channel moves a ready
tenant back. The step follows from the work of the tenant's staff and of global
admins.
