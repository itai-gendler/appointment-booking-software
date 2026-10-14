---
domain: calendar
availability:
  - { place: web::booking-site }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/book-appointment/[[id]]/(components)/utils.ts" }
  - { kind: code, role: implementation, target: "src/lib/client/appointment-crypto.ts#UnifiedAppointmentCrypto" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/create-new-client/+server.ts" }
  - { kind: code, role: implementation, target: "src/routes/api/tenants/[id]/appointments/add-to-tunnel/+server.ts" }
  - { kind: code, role: implementation, target: "src/lib/server/services/appointment-service.ts#AppointmentService" }
  - { kind: doc, role: intent, target: "docs/client-side-encryption-concept.md" }
---

# Book appointment

A client books on the tenant's booking site: an appointment type, an agent or
no preference, a free slot, their details, and a PIN to create their client
account or log in to it. In a channel that requires confirmation the booking is
a request until staff confirm it.
