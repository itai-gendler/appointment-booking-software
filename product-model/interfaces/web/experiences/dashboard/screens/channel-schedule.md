---
entities:
  - { entity: channel, shows: [Schedule], collects: [Schedule] }
entryPoints:
  - web: "/dashboard/channels/{channelId}/slots"
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/[channelId]/slots/+page.svelte" }
---

# Channel schedule

A channel's weekly slot templates.
