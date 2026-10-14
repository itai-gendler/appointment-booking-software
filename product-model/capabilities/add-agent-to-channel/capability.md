---
domain: channels
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/channel-service.ts#ChannelService" }
---

# Add agent to channel

A tenant admin lets clients book an agent in a channel. A channel needs at
least one agent.
