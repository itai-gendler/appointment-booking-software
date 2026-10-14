---
appliesTo:
  - { type: entity, id: notification, effect: removes }
permits:
  - related: [{ verb: receives, entity: member }, { verb: holds, entity: staff-member }]
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/notification-service.ts#NotificationService" }
---

# Staff members clear only their own notifications

Each staff member marks their own notifications as read.
