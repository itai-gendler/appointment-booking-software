---
appliesTo:
  - { type: capability, id: create-admin-account }
  - { type: entity, id: account, effect: creates, contexts: [{ place: web::staff-sign-in }] }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/setup/create-admin-account/+page.server.ts" }
---

# A server is set up once

The first-run setup creates the first global admin only while the server has none.
