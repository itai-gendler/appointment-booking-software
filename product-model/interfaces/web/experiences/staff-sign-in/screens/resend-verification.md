---
entities:
  - { entity: account, collects: [E-mail address] }
entryPoints:
  - web: /confirm/resend
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/confirm/resend/+page.server.ts" }
---

# Resend verification e-mail

Where a person whose link was wrong or outdated asks for a new one.
