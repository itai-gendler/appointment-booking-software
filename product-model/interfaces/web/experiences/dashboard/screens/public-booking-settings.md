---
entities:
  - { entity: channel, shows: [Public, Requires confirmation], collects: [Public, Requires confirmation] }
entryPoints:
  - web: "/dashboard/channels/{channelId}/public-booking"
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/[channelId]/public-booking/+page.svelte" }
---

# Public booking settings

Whether a channel is open to public booking and whether its appointments need
confirmation.
