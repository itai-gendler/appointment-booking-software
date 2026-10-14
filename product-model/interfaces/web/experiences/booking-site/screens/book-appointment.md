---
entities:
  - { entity: channel, shows: [Name, Description, Requires confirmation] }
  - { entity: agent, shows: [Name, Description, Image] }
  - { entity: tenant, shows: [Name, Visitor address, Phone number required] }
  - { entity: appointment, shows: [Date and time, Duration], collects: [Date and time, Name, E-mail address, Phone number, E-mail updates] }
  - { entity: client, collects: [E-mail address, PIN] }
entryPoints:
  - web: /book-appointment
  - web: "/book-appointment/{channel}"
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/book-appointment/[[id]]/+page.svelte" }
---

# Book appointment

The booking flow: appointment type, agent, slot, personal data, PIN, summary
and completion.
