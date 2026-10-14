---
domain: notifications
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/lib/components/layouts/sidebar-layout/components/notification-item.svelte" }
  - { kind: code, role: implementation, target: "src/lib/stores/notifications.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/notifications/[notificationId]/+server.ts" }
---

# Mark notification as read

A staff member marks a notification as read, which takes it off their list.
