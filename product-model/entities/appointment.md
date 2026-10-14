---
domain: calendar
relations:
  - { entity: notification, verb: concerns, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/tenant-schema.ts#appointment" }
  - { kind: code, role: implementation, target: "src/lib/utils/appointments.ts#serverAppointmentStatusToUiFilterStatus" }
---

# Appointment

A client's appointment with an agent in a channel. Its client details are
encrypted on the client's or staff member's device; only the client and staff
members with access can read them.

## Information kept

- **Date and time** — when it starts
- **Duration** — its length in minutes, the slot duration of the channel's schedule
- **Time zone** — the time zone it was booked in
- **Name** — the client's name, 2 to 50 characters
- **E-mail address** — the client's e-mail address
- **Phone number** — the client's phone number in international format; optional unless the tenant requires it
- **Language** — the language the client books in and is written to in
- **E-mail updates** — whether the client wants to be notified of changes by e-mail
- **Progress** — how the appointment is going on the day: Not here yet, Waiting, In Progress or Done
- **Reminder sent** — when the client was reminded of it, if they were
- **Booked at** — when it was booked

## States

### Requested

Booked in a channel that requires confirmation, and waiting for staff to confirm or deny it. Shown to the client as requested.

### Confirmed

Booked: confirmed by staff, or booked where no confirmation is required.
