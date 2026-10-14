---
domain: notifications
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/lib/components/layouts/sidebar-layout/components/notification-item.svelte" }
  - { kind: code, role: implementation, target: "src/lib/stores/notifications.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/notifications/+server.ts" }
---

# Mark all notifications as read

A staff member clears all their notifications at once.
