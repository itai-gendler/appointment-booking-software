---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: capability, id: add-appointment }
  - { type: capability, id: confirm-appointment }
  - { type: capability, id: deny-appointment }
  - { type: capability, id: move-appointment }
  - { type: capability, id: cancel-appointment }
  - { type: capability, id: send-appointment-reminders }
references:
  - { kind: code, role: implementation, target: "src/lib/server/email/email-service.ts" }
---

# Clients are e-mailed only when they asked to be notified

Booking, request, confirmation, rejection, update, cancellation and reminder
e-mails go to a client only when the appointment says they want updates by
e-mail. Otherwise the address never reaches the mail server, and the client
logs in to check for changes.
