---
domain: absences
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/absences/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/agent-service.ts#AgentService" }
---

# Delete absence

A staff member deletes an absence; the agent is available again in that timespan.
