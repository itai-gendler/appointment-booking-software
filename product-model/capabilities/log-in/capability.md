---
availability:
  - { place: web::staff-sign-in }
references:
  - { kind: code, role: implementation, target: "src/routes/api/auth/login/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/login/+page.svelte" }
---

# Log in

Staff members and global admins log in to the dashboard with a passkey; a
global admin who set a passphrase may use it instead. Staff members log in at
their tenant's domain.
