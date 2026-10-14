---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member enters their e-mail address and chooses Resend E-Mail
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::staff-sign-in::resend-verification
  - text: "The Product e-mails a new confirmation link to the Account's address"
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: reads, facts: [E-mail address, E-mail language] }
    contexts:
      web:
        place: web::staff-sign-in::resend-verification
---

# Request a new verification link

## Trigger

A person's link failed and they chose Request new E-Mail.

## Outcome

A new link is on its way to the address.
