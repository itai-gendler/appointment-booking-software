---
availability:
  - { place: web::client-area }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/clients/(components)/appointment-list.svelte" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/my-appointments/+server.ts" }
---

# Browse my appointments

A signed-in client sees their upcoming appointments with the tenant, requested
or confirmed, decrypted on their device.
