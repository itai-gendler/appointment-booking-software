---
availability:
  - { place: web::booking-site }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/clients/login/client-login-form.svelte" }
  - { kind: code, role: implementation, target: "src/lib/client/appointment-crypto.ts#UnifiedAppointmentCrypto" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/verify-challenge/+server.ts" }
---

# Log in as client

A client who booked before signs in with their e-mail address and PIN to see
their appointments. Repeated wrong PINs pause further attempts.
