---
kind: person
acts: internal
relations:
  - { entity: account, verb: uses, cardinality: one-to-one }
  - { entity: member, verb: holds, cardinality: one-to-one }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/staff/(components)/utils.ts" }
---

# Staff member

A person working for one tenant who signs in to its dashboard. What they may
do there follows the role their membership holds.
