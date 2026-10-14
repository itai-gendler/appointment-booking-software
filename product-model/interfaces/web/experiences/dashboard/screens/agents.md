---
entities:
  - { entity: agent, shows: [Name, Description, Image], collects: [Name, Description, Image] }
entryPoints:
  - web: /dashboard/agents
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/agents/+page.svelte" }
---

# Agents

The tenant's agents, where they are added, edited and deleted.
