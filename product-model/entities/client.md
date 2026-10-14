---
kind: person
acts: external
relations:
  - { entity: appointment, verb: books, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "src/lib/server/db/tenant-schema.ts#clientAppointmentTunnel" }
  - { kind: doc, role: context, target: "docs/client-side-encryption-concept.md" }
---

# Client

A person booking appointments with a tenant. Their first booking creates their
client account at that tenant, protected by a PIN only they know.

## Information kept

- **E-mail address** — identifies them at this tenant; the server keeps only a fingerprint of it
- **PIN** — six digits they chose; it never leaves their device
