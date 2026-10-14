---
domain: agents
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/agents/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/agent-service.ts#AgentService" }
---

# Edit agent

A tenant admin updates an agent's public details.
