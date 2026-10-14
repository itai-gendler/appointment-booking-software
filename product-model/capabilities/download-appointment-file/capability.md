---
availability:
  - { place: web::dashboard }
  - { place: web::booking-site }
references:
  - { kind: code, role: implementation, target: "src/lib/utils/ics.ts" }
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/book-appointment/[[id]]/(components)/complete.svelte" }
---

# Download appointment file

An appointment is downloaded as a calendar file: by a client after booking
(Add to Calendar) or by a staff member from the calendar (Download as file).
