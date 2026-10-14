---
entities:
  - { entity: appointment, shows: [Date and time, Duration, Name, E-mail address, Phone number, Language, Progress], collects: [Name, E-mail address, Phone number, E-mail updates, Progress] }
  - { entity: channel, shows: [Name, Color] }
  - { entity: agent, shows: [Name] }
entryPoints:
  - web: /dashboard/calendar
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/+page.svelte" }
---

# Calendar

The tenant's calendar by day or week: booked, requested and available slots per
channel, and the details of each appointment.
