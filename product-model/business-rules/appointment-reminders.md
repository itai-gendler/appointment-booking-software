---
appliesTo:
  - { type: capability, id: send-appointment-reminders }
  - { type: entity, id: appointment, effect: changes, facts: [Reminder sent] }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/(components)/EmailReminder.svelte" }
---

# Each confirmed appointment is reminded once

Reminders go out for confirmed appointments from now until the end of
tomorrow that were not booked today and have not been reminded yet.
