---
availability:
  - { place: web::dashboard }
  - { place: web::client-area }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/logout/+page.svelte" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/dashboard/(components)/InactivityWarning.svelte" }
  - { kind: code, role: implementation, target: "src/lib/stores/auth.ts" }
---

# Log out

A signed-in person ends their session: a staff member or global admin leaves
the dashboard, a client leaves their appointments. The dashboard also logs a
person out after a quarter of an hour without activity, warning them first.
