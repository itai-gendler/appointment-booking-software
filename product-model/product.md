---
id: open-reception
summary: End-to-end encrypted appointment booking for organizations, with a public booking site per tenant and a dashboard for its staff.
category: appointment-booking
tags: [appointments, booking, end-to-end-encryption, multi-tenant]
authors:
  - { name: OpenReception, url: "https://open-reception.org" }
license: AGPL-3.0
languages: [en, de]
limitations:
  - Client details are end-to-end encrypted, so only the client and the staff members granted access read them; global admins and the server never do.
  - Each tenant is reached at its own domain, and its staff members sign in there.
  - Clients sign in with their e-mail address and a six-digit PIN; staff members sign in with passkeys, and only global admins may also use a passphrase.
  - Absences do not inform clients or move appointments already booked; staff cancel those themselves.
  - Clients receive e-mails only when they chose to be notified of changes by e-mail.
references:
  - { kind: doc, role: intent, target: README.md }
  - { kind: doc, role: context, target: docs/client-side-encryption-concept.md }
  - { kind: code, role: implementation, target: project.inlang/messages/en.json }
---

# OpenReception

OpenReception is an end-to-end encrypted appointment booking platform. One
server hosts several tenants — the organizations or individuals collecting
appointments — each reached at its own domain. A tenant's clients book
appointments on its public booking site by choosing a channel, an agent and a
free slot; the tenant's staff members confirm, move, cancel and follow those
appointments in a calendar on the dashboard. Global admins run the server and
its tenants.

## Intent

"End-to-end encrypted appointment booking platform to collect appointments for
your organization." Tenants are "the organizations/individuals that will
collect appointments"; channels are "your way to collect different types of
appointments"; agents "let your clients choose which person, team or group they
want to make an appointment with". A client's details are visible only to the
client and the tenant: "Only you and the organization will be able to access
this information. It is end-to-end encrypted."
