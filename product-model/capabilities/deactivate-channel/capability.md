---
domain: channels
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/channel-service.ts#ChannelService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/(components)/pause-channel-form/pause-channel-form.svelte" }
---

# Deactivate channel

A tenant admin stops a channel from offering and accepting new appointments,
keeping its configuration.
