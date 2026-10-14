---
domain: channels
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/channel-service.ts#ChannelService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/(components)/delete-channel-form/delete-channel-form.svelte" }
---

# Delete channel

A tenant admin deletes a channel after typing its name; the page suggests
deactivating it instead.
