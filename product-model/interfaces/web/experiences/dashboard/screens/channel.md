---
entities:
  - { entity: channel, shows: [Name, Description, Agents, Notified staff], collects: [Name, Description, Agents, Notified staff] }
  - { entity: agent, shows: [Name] }
  - { entity: member, shows: [Role] }
entryPoints:
  - web: "/dashboard/channels/{channelId}"
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/[channelId]/+page.svelte" }
---

# Channel

One channel: its name and description, agents, and the staff members it
notifies, with links to its schedule and public booking settings.
