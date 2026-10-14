---
domain: channels
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/channel-service.ts#ChannelService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/(components)/edit-channel-form/edit-channel-form-public-booking.svelte" }
---

# Change public booking settings

Whether anyone can book in a channel on the booking site, and whether its
appointments must be confirmed by staff.
