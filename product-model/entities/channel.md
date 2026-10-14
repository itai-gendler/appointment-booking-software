---
domain: channels
relations:
  - { entity: appointment, verb: receives, cardinality: one-to-many }
  - { entity: agent, verb: offers, cardinality: many-to-many }
  - { entity: member, verb: notifies, cardinality: many-to-many }
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/tenant-schema.ts#channel" }
  - { kind: code, role: implementation, target: "src/lib/server/services/channel-service.ts#ChannelService" }
---

# Channel

A type of appointment a tenant collects, with the agents who serve it and the
weekly schedule its slots are made from.

## Information kept

- **Name** — kept per language
- **Description** — optional, kept per language; helps clients understand when to book in this channel
- **Color** — the color its appointments carry in the calendar
- **Agents** — the agents clients can book in this channel
- **Schedule** — slot templates, each with weekdays, a from and a to time, and a slot duration in minutes; slots are made from them
- **Public** — whether anyone can book in this channel on the booking site
- **Requires confirmation** — whether appointments booked here must be confirmed by staff
- **Notified staff** — the staff members notified of this channel's appointments

## States

### Active

Offers and accepts new appointments.

### Deactivated

Neither offers nor accepts new appointments.
