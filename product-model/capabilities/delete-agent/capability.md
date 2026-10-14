---
domain: agents
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/agents/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/agent-service.ts#AgentService" }
---

# Delete agent

A tenant admin deletes an agent after typing its name. The agent leaves every
channel and is no longer offered; appointments already booked with it stay.
