---
kind: edge
routes:
  web: Web
steps:
  - text: "The Staff member types the agent's name to confirm and deletes it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::agents
  - text: The Product deletes the Agent and returns the Tenant to its agents step
    kind: product
    actor: staff-member
    entities:
      - { entity: agent, effect: removes }
      - { entity: tenant, effect: changes, from: Ready, to: Awaiting agents, facts: [] }
    contexts:
      web:
        place: web::dashboard::agents
---

# Delete a ready tenant's last agent

## Trigger

A tenant admin deletes the only agent of a ready tenant.

## Outcome

The agent is gone and the tenant is back at its agents step; the booking site stops offering appointments.
