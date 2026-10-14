---
domain: agents
relations:
  - { entity: appointment, verb: attends, cardinality: one-to-many }
  - { entity: absence, verb: has, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/tenant-schema.ts#agent" }
---

# Agent

A person, team or working group clients make an appointment with. Agents are
required participants in appointments, and their details are public.

## Information kept

- **Name** — 2 to 50 characters
- **Description** — optional titles, roles or other information that helps clients choose, kept per language
- **Image** — an optional picture
