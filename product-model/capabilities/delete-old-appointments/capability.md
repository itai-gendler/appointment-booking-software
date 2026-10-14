---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/startup-service.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
---

# Delete old appointments

Twice a day the Product deletes every appointment whose date lies further back
than the tenant's retention period.
