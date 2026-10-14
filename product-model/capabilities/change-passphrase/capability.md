---
domain: account
availability:
  - { place: web::dashboard }
references:
  - { kind: code, role: implementation, target: "src/routes/api/me/passphrase/+server.ts" }
---

# Change passphrase

A global admin sets or changes the passphrase they may log in with instead of a
passkey.
