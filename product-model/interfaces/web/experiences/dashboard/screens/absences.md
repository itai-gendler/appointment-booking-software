---
entities:
  - { entity: absence, shows: [Kind, Reason, Start, End, Weekdays, Time window], collects: [Kind, Reason, Start, End, Weekdays, Time window] }
  - { entity: agent, shows: [Name] }
entryPoints:
  - web: /dashboard/absences
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/absences/+page.svelte" }
---

# Absences

The agents' future absences.
