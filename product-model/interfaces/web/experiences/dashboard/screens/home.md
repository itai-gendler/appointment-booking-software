---
entities:
  - { entity: tenant, shows: [Name] }
  - { entity: appointment, shows: [Reminder sent] }
entryPoints:
  - web: /dashboard
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/+page.svelte" }
---

# Dashboard home

The dashboard's start page: the onboarding guide while the tenant is being set
up, and the appointment reminders card once it is ready.
