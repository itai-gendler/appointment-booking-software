---
domain: absences
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/tenant-schema.ts#agentAbsence" }
---

# Absence

A period in which an agent is unavailable, so no slots are offered for them.

## Information kept

- **Kind** — One-Time, for vacations and the like, or Recurring, every week
- **Reason** — internal: Public Holiday, Vacation, Sick Leave, Training/Education, Off-Site or Other
- **Start** — when it begins, or the first day of a recurring absence
- **End** — when it ends, or the last day of a recurring absence; after the start and in the future
- **Weekdays** — for a recurring absence, the weekdays it applies on
- **Time window** — for a recurring absence, the from and to time on those weekdays, or all day
