---
domain: notifications
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/lib/components/layouts/sidebar-layout/components/notification-item.svelte" }
  - { kind: code, role: implementation, target: "src/lib/stores/notifications.ts" }
---

# Open notification

A staff member opens one of their notifications and the calendar shows its
appointment.
