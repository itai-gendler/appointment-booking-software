---
appliesTo:
  - { type: capability, id: book-appointment }
  - { type: capability, id: log-in-as-client }
references:
  - { kind: code, role: implementation, target: "src/routes/(pages)/(clients)/book-appointment/[[id]]/(components)/auth/schema.ts" }
  - { kind: code, role: implementation, target: "src/lib/const/pin.ts" }
---

# A client's PIN is six digits and hard to guess

The PIN is exactly six digits and not one of a list of easily guessed PINs. It never leaves the client's device; repeated wrong PINs pause further attempts.
