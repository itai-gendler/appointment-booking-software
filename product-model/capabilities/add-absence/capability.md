---
domain: absences
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/absences/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/agent-service.ts#AgentService" }
---

# Add absence

A staff member marks an agent unavailable, once for a period or every week in a
time window. Clients are not informed, and appointments already booked must be
cancelled by hand.
