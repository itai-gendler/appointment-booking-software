---
entities:
  - { entity: notification, shows: [Kind] }
  - { entity: appointment, shows: [Date and time, Name, E-mail address, Phone number] }
  - { entity: channel, shows: [Name] }
references:
  - { kind: code, role: implementation, target: "src/lib/components/layouts/sidebar-layout/components/notifications.svelte" }
---

# Notifications

The staff member's notifications, each with its channel and, once decrypted,
the client's details.
