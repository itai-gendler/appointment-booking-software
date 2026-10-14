---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: entity, id: channel, facts: [Public] }
references:
  - { kind: code, role: implementation, target: "src/routes/api/public/channels/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/schedule-service.ts#ScheduleService" }
---

# The booking site offers only active public channels of a ready tenant

Clients can book only once the tenant is ready. They are offered channels that
are public, active and have at least one agent, and slots made from the
channel's schedule, without the agents' absences and existing appointments.
