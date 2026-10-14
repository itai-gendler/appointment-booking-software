---
kind: person
acts: internal
relations:
  - { entity: account, verb: uses, cardinality: one-to-one }
references:
  - { kind: code, role: implementation, target: "src/lib/server/utils/permissions.ts#checkPermission" }
---

# Global Admin

A person who runs this server: sets it up, adds and removes tenants, and
manages any tenant's settings, agents, channels and staff after selecting it.
A global admin never reads client details.

## Information kept

- **Selected tenant** — the tenant they are currently managing in the dashboard, or none
