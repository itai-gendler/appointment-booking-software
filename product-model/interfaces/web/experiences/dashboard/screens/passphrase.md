---
entities:
  - { entity: account, collects: [Passphrase] }
entryPoints:
  - web: /dashboard/account/change-passphrase
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/account/change-passphrase/+page.svelte" }
---

# Change passphrase

Where a global admin sets their backup passphrase.
