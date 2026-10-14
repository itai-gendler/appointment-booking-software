---
entities:
  - { entity: channel, shows: [Name, Description], collects: [Name, Description] }
entryPoints:
  - web: /dashboard/channels
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/channels/+page.svelte" }
---

# Channels

The tenant's channels, marked when deactivated or incomplete.
