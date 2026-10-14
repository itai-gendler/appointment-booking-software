---
appliesTo:
  - { type: entity, id: appointment, effect: changes }
permits:
  - related: [{ verb: receives, entity: channel }, { verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/utils.ts" }
---

# Only the tenant's staff members confirm, move and follow appointments

Confirming, moving and recording the progress of appointments is the work of tenant admins and appointment managers.
