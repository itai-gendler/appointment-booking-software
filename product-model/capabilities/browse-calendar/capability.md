---
domain: calendar
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/calendar/+page.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/calendar/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/schedule-service.ts#ScheduleService" }
---

# Browse calendar

Staff members see the tenant's calendar by day or week, per channel, with
booked, requested and available slots. Client details are decrypted on their
device when they have access.
