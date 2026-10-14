---
kind: primary
routes:
  web: Web
steps:
  - text: The Staff member chooses Resend Invite for the colleague and confirms
    kind: actor
    actor: staff-member
    entities: []
    contexts:
      web:
        place: web::dashboard::staff
  - text: The Product e-mails a new link to the invited Account
    kind: product
    actor: staff-member
    entities:
      - { entity: account, effect: reads, facts: [E-mail address, E-mail language] }
    contexts:
      web:
        place: web::dashboard::staff
---

# Resend an invitation

## Trigger

An invited colleague's link expired.

## Outcome

A new invitation link is on its way to the colleague.
