---
domain: agents
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/agents/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/agent-service.ts#AgentService" }
---

# Add agent

A tenant admin adds a person, team or working group clients can make appointments with.
