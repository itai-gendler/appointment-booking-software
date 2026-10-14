---
domain: channels
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/channel-service.ts#ChannelService" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/(components)/edit-channel-form/edit-channel-form-slots.svelte" }
  - { kind: code, role: implementation, target: "src/lib/server/services/schedule-service.ts#ScheduleService" }
---

# Edit channel schedule

A tenant admin sets the weekly slot templates a channel's slots are made from:
weekdays, a from and a to time, and the slot duration.
