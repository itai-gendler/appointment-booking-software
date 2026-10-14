---
appliesTo:
  - { type: capability, id: delete-old-appointments }
  - { type: entity, id: tenant, facts: [Appointment retention] }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/tenant-admin-service.ts#TenantAdminService" }
  - { kind: code, role: implementation, target: "src/lib/server/services/startup-service.ts" }
---

# Appointments are deleted after the tenant's retention period

Appointments whose date lies further back than the tenant's retention period, 30 days unless changed, are deleted twice a day.
