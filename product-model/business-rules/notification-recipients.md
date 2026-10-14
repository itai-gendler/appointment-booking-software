---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: capability, id: confirm-appointment }
  - { type: capability, id: cancel-appointment }
references:
  - { kind: code, role: implementation, target: "src/lib/server/services/notification-service.ts#NotificationService" }
---

# Notifications go to the staff a channel notifies

New appointment requests, staff confirmations and client cancellations notify
the staff members chosen in the channel's notifications; a new request also
e-mails them. A channel that notifies nobody creates no notification.
