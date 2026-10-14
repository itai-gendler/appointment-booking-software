---
domain: account
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/api/me/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/account/general/+page.server.ts" }
---

# Change account settings

A person changes their own name and the language OpenReception e-mails them in.
