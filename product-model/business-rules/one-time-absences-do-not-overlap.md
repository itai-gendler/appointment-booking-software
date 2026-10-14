---
appliesTo:
  - { type: capability, id: add-absence }
  - { type: capability, id: edit-absence }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/agent-service.ts#AgentService" }
---

# An agent's one-time absences never overlap

A one-time absence overlapping another one-time absence of the same agent is refused; recurring absences may overlap.
