---
type: web
actors: [client, staff-member, global-admin]
entryPoints:
  - web: /
references:
  - { kind: code, role: implementation, target: src/lib/const/routes.ts }
  - { kind: code, role: implementation, target: src/server-hooks/authGuard.ts }
---

# OpenReception web app

The web app at a tenant's domain: the public booking site where clients book and
manage their appointments, and the dashboard where staff members and global
admins sign in to run the tenant and the server.
