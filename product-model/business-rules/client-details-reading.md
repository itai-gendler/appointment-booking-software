---
appliesTo:
  - { type: entity, id: appointment, effect: reads, facts: [Name, E-mail address, Phone number] }
permits:
  - related: [{ verb: books, entity: client }]
  - related: [{ verb: receives, entity: channel }, { verb: has, entity: tenant }, { verb: has, entity: member }, { verb: holds, entity: staff-member }]
    when:
      - { entity: member, fact: Access, is: Granted }
references:
  - { kind: doc, role: intent, target: "docs/client-side-encryption-concept.md" }
  - { kind: code, role: implementation, target: "src/lib/client/appointment-crypto.ts#UnifiedAppointmentCrypto" }
---

# Only the client and staff members with access read client details

An appointment's client details are encrypted on the device of the client or
staff member who enters them. They are readable by the client who booked it and
by the tenant's staff members who were granted access; global admins and the
server never read them.
