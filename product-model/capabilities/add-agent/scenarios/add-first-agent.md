---
kind: primary
routes:
  web: Web
steps:
  - text: "The Staff member enters the agent's name and adds it"
    kind: actor
    actor: staff-member
    entities:
      - { entity: agent, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::agents
  - text: The Product adds the Agent and moves the Tenant on to its channel step
    kind: product
    actor: staff-member
    entities:
      - { entity: agent, effect: creates, facts: [Name, Description, Image] }
      - { entity: tenant, effect: changes, from: Awaiting agents, to: Awaiting channel, facts: [] }
      - { entity: channel, effect: reads, facts: [] }
    contexts:
      web:
        place: web::dashboard::agents
---

# Add the first agent of a new tenant

## Trigger

A tenant admin follows the onboarding guide after saving the settings.

## Outcome

The agents step is done; the guide moves on to channels.
