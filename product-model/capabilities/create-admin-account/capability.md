---
availability:
  - { place: web::staff-sign-in }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/setup/create-admin-account/+page.server.ts" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/+page.server.ts" }
---

# Create admin account

The first-run setup of a new server: the first global admin creates their
account with a passkey or a passphrase, and confirms it through an emailed link.
The setup exists only while the server has no global admin.
