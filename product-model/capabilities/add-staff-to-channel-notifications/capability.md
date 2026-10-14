---
domain: channels
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/channel-service.ts#ChannelService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/(components)/edit-channel-form/edit-channel-form-notifications.svelte" }
---

# Add staff to channel notifications

A tenant admin chooses a staff member to be notified about a channel's
appointment requests, confirmations and cancellations.
